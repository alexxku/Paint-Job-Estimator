# Paint-Job-Estimator
Using C# console application, a painting company has determined that for every 115 square feet of wall space, one gallon of paint and eight hours of labor will be required. The company charges $20.00 per hour for labor. Design a modular program that asks the user to enter the square feet of wall space to be painted and the price of the paint per gallon. The program should display the following data:   The number of gallons of paint required.  The hours of labor required.  The cost of the paint  The labor charges. The total cost of the paint job.


using System;

namespace PaintJobEstimator
{

    class Program
    {
        static void Main(string[] args)
        {
            //Variable declarations and assignments
            int hours = 8, gallons = 1, feet = 115;
            double tHour, tPaints, feetReq;
            double paintPrice, tCharge, tCostPaints, tJobCosts;

            //Display default information
            Console.WriteLine("A painting company has determined that for every 115 square feet of wall space, " +
                "\none gallon of paint and eight hours of labor will be required.\n");

            //Ask user for input
            Console.WriteLine("Enter the square feet of wall space to be painted and the price of the paint per gallon. \n");
            Console.Write("Square feet of wall space: ");
            feetReq = Convert.ToDouble(Console.ReadLine());
            Console.Write("Price of paint per gallon: $");
            paintPrice = Convert.ToDouble(Console.ReadLine());

            //Calculations
            tHour = Math.Round(tHours(feet, hours, feetReq), 2);
            tCharge = Math.Round(tCharges(tHour), 2);
            tPaints = Math.Round(tPaint(feetReq, feet, gallons), 2);
            tCostPaints = Math.Round(tCostPaint(paintPrice, tPaints), 2);
            tJobCosts = Math.Round(tJobCost(tCostPaints, tCharge), 2);

            //Display answers to user
            Console.Write($"\n\nTotal number of gallons required: {tPaints} gallons\n");
            Console.Write($"\nThe total hours of labor required: {tHour} hours\n");
            Console.Write($"\nThe total cost of paint: ${tCostPaints}\n");
            Console.Write($"\nTotal labor charges: ${tCharge}\n");
            Console.Write($"\nTotal cost of job: ${tJobCosts}\n");
            Console.ReadLine();
        }

        //Static methods do not belong to a specific object

        //Total hours of labor
        public static double tHours(int ft, int hr, double ftR)
        {
            return (ftR * hr) / ft;
        }
        //Labor Charges
        public static double tCharges(double tHr)
        {
            return tHr * 20.00;
        }
        //The number of gallons of paint required
        public static double tPaint (double ftR, int ft, int g)
        {
            return (ftR * g) / ft;
        }
        //The total cost of paint
        public static double tCostPaint(double p, double tP)
        {
            return tP* p;
        }
        //The total cost of job
        public static double tJobCost (double tCP, double tC)
        {
            return tCP + tC;
        }
    }
}
