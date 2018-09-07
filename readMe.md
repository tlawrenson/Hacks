#include <stdio.h>

int main(void) {
  //create all variables
  int currentDay, daysLeft;
  double totalGB, usedGB, averageDailyUse, allowedGB, dailyGB, overageAmount, underAmount, newAverageDailyUse;
  //ask all three questions for cell plan data
  printf("How many total GB do you receive each 30 day period?\n");
  scanf("%lf", &totalGB);

  printf("What day in your cycle are you?(1-30)\n");
  scanf("%d", &currentDay);

  printf("How many GB have you used so far?\n");
  scanf("%lf", &usedGB);
  //complete all mathematic operations to find values not scanned
  daysLeft = 30-currentDay;

  dailyGB = totalGB/30;

  averageDailyUse = usedGB/currentDay;

  overageAmount = (averageDailyUse*30) - totalGB;

  underAmount = totalGB - (averageDailyUse*30);

  newAverageDailyUse = (totalGB - usedGB)/daysLeft;

  printf("%d days into you cycle, %d days left in you cycle.  Average daily use: %lf\n", currentDay, daysLeft, averageDailyUse);
  //print statements giving customer all information that was calculated
  if(averageDailyUse > dailyGB){
    printf("You are currently exceeding your recommended average daily use. (%lf)  If you continue with your current average daily use, you will exceed your current plan by %lf GB.\n", dailyGB, overageAmount);
    printf("In order to stay within your data limit, it is recommended that you use %lf GB a day from now on.\n", newAverageDailyUse);
  }else if(averageDailyUse < dailyGB){
    printf("You are currently below your recommended average daily use. (%lf)  If you continue with your current average daily use, you will fall below you current plan by %lf GB\n", dailyGB, underAmount);
    printf("In order to use all of your data by the end of the cycle, it is recommended that you use %lf GB a day from now on./n", newAverageDailyUse);
  }else{
    printf("You are currently at your recommended average daily use. (%lf)  If you continue with your current average daily use, you will efficiently use all of your data, and no more, by the last day of your cycle.\n", dailyGB);
  }
  

  return 0;
}
