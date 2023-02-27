---
layout: post
title:  "Hurricane-analyzer"
date:   2023-02-25 00:05:01 +0900
categories: Java
---
## Introduction

This is a code used to anaylze datas including occured year, month pressure, windspeed, name, and category level. If the file named hurricanedata.txt is shown in the same folder, the proram
will open the file and start to analyze it. ArrayList, arrays, for each loop is used in this program.

## Codeblock 1

``` java
import java.io.IOException;
import java.io.PrintWriter;
import java.io.File;
import java.util.Scanner;
import java.util.ArrayList;
public class HurricaneTester

{

    public static void main(String[] args) throws IOException
    {
        File fileName = new File("hurricanedata.txt");
        Scanner inFile = new Scanner(fileName);
        Scanner in = new Scanner(System.in);
        int numValues = 0;
        boolean p = true;
        int year1 = 0;
        int year2 = 0;
        int tmp;
        while (inFile.hasNextLine() )
        {
            inFile.nextLine();
            numValues++;
        }
        inFile.close();
        int [] years = new int[numValues];
        String [] months = new String[numValues];
        int [] pressures = new int[numValues];
        double [] windSpeeds = new double[numValues];
        String [] names = new String[numValues];
        int [] categories = new int [numValues];
        int cnt = 0;
        double average = 0;
        double average1 = 0;
        double average2 = 0;
        int mn1 = Integer.MAX_VALUE;
        int mx1 = Integer.MIN_VALUE;
        int mn2 = Integer.MAX_VALUE;
        int mx2 = Integer.MIN_VALUE;
        double mx3 = Double.MIN_VALUE;
        double mn3 = Double.MAX_VALUE;
        int [] cat = new int[5];
        inFile = new Scanner(fileName);
        int index = 0;
        while(inFile.hasNext() )
        {
            years[index] = inFile.nextInt();
            months[index] = inFile.next();
            pressures[index] = inFile.nextInt();
            windSpeeds[index] = inFile.nextDouble();
            names[index] = inFile.next();
            index++;
        }
        inFile.close();
        for(int i = 0; i < numValues; i++){
            windSpeeds[i] *= 1.15078;
            if(windSpeeds[i] >= 74 && windSpeeds[i] <= 95){
                categories[i] = 1;
            }
            else if(windSpeeds[i] >= 96 && windSpeeds[i] <= 110){
                categories[i] = 2;
            }
            else if(windSpeeds[i] >= 111 && windSpeeds[i] <= 129){
                categories[i] = 3;
            }
            else if(windSpeeds[i] >= 130 && windSpeeds[i] <= 156){
                categories[i] = 4;
            }
            else if(windSpeeds[i] >= 157){
                categories[i] = 5;
            }
        }
        ArrayList<Hurricane> hr = new ArrayList<Hurricane>();
        for(int i = 0; i < numValues; i++){
            hr.add(new Hurricane(years[i], names[i], months[i], categories[i], pressures[i], windSpeeds[i]));
        }
        
        while(p){
            System.out.println("Please enter two numbers for the range of year from 1995 to 2019");
            year1 = in.nextInt();
            year2 = in.nextInt();
            if((year1 >= 1995 && year1 <= 2019) && (year2 >= 1995 && year2 <= 2019)){
            tmp = year2;
            p = false;
            if(year1 > year2){
                year2 = year1;
                year1 = tmp;
            }
            }
        }
        System.out.println("Year        Hurricane      Category     Presure  (mb)     WindSpeed   (mph)");
        System.out.println("=====================================================================================");
        for(int i = 0; i < numValues; i++){
            if(hr.get(i).getYear() >= year1 && hr.get(i).getYear() <= year2){
                System.out.print(hr.get(i).toString());
                cnt++;
                average +=  hr.get(i).getCat();
                average1 += hr.get(i).getPressure();
                average2 += hr.get(i).getWindspeed();
                for(int j = 1; j <= 5; j++){
                    if(hr.get(i).getCat() == j){
                        cat[j - 1] ++;
                    }
                }
                if(mx1 < hr.get(i).getCat()){
                    mx1 =  hr.get(i).getCat();
                }
                if(mn1 >  hr.get(i).getCat()){
                    mn1 =  hr.get(i).getCat();
                }
                if(mx2 <  hr.get(i).getPressure()){
                    mx2 =  hr.get(i).getPressure();
                }
                if(mn2 >  hr.get(i).getPressure()){
                    mn2 =  hr.get(i).getPressure();
                }
                if(mx3 <  hr.get(i).getWindspeed()){
                    mx3 =  hr.get(i).getWindspeed();
                }
                if(mn3 >  hr.get(i).getWindspeed()){
                    mn3 =  hr.get(i).getWindspeed();
                }
            }
        }
        average /= cnt;
        average1 /= cnt;
        average2 /= cnt;
        
        System.out.println("==========================================================");
        System.out.printf(" %8s%8.2f %8.2f %8.2f%n", "Average:", average, average1, average2);
        System.out.printf(" %8s%8d %8d %8.2f%n", "Minimum:", mn1, mn2, mn3);
        System.out.printf(" %8s%8d %8d %8.2f%n", "Maximum:", mx1, mx2, mx3);
        System.out.println("Summary of categories:  ");
        for(int i = 0; i < 5; i++){
            System.out.printf(" %8s%2d%s %8d%n", "Cat", i + 1,":", cat[i]);
        }
        
        
        
     }
}
```

## Codeblock 2

``` java
public class Hurricane
{
   private String name, month;
   private int year;
   private int cat;
   private int pressure;
   private double windspeed;

     
   
   public Hurricane(int y, String n, String m, int c, int p, double w) {
      this.year = y;
      this.name = n;
      this.month = m;
      this.cat = c;
      this.pressure = p;
      this.windspeed = w;
   }

   public int getYear() {
      return year; 
   }

   public String getName() {
      return name; 
   }
   
   public String getMonth() {
      return month;  
   }
   
   public int getCat() {
      return cat;  
   }
   
   public int getPressure() {
      return pressure;
   }

   public double getWindspeed() {
      return windspeed;
   }
   
   public void setYear(int y) {
      year = y;
   }
   
   public void setName(String n) {
      name = n;
   }
   
   public void setMonth(String m) {
      month = m;
   }
   
   public void setCat(int c) {
      cat = c;
   }
   
   public void setPressure(int p) {
      pressure = p;
   }
   
   public void setWindspeed (double w) {
      windspeed = w;
   }


   public String toString() {
       return String.format("%d %16s %9d  %15d %15.3f %n", getYear(), getName(), getCat(), getPressure(), getWindspeed());
   }
    
}
```
