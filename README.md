# Exceptional-Handling
program to implement try catch block to show exceptional handling
--------------------------------------------------------------------------------------------
package simpleInterestException;

import java.util.Scanner;


/**
 * @Preeti: This is a simple interest program which implements exceptional handling when a user enters 0 value for 
 * principle,rate or time.
 * Also it does exceptional handling when multiplication of principle, rate and time is less than 100.
 */
public class SimpleInterest {

	int principle;
	int rate;
	int time;
	static int x = 0;

	public static void simpleInterest(int principle, int rate, int time) {

		if (principle == 0 || rate == 0 || time == 0) {
			throw new ArithmeticException();

		}
		int m = (principle * rate * time);
		if (m <= 100) {
			throw new ArrayIndexOutOfBoundsException();

		}
		int SI = (principle * rate * time) / 100;

		System.out.println("simple interest is:" + SI);
	}

	public static void main(String args[]) {
		while (true) {
			System.out.println("please enter principle,rate and time");
			Scanner sc = new Scanner(System.in);
			int p = sc.nextInt();
			int r = sc.nextInt();
			int t = sc.nextInt();

			// SimpleInterest si=new SimpleInterest();
			// si.simpleInterest(p,r,t);

			while (true) {
				try {
					simpleInterest(p, r, t);
				} catch (ArithmeticException e) {

					System.out
							.println("principle or rate or time cannot be zero");
				} catch (ArrayIndexOutOfBoundsException e) {

					System.out.println("should be greater than 100");
				}
				return;
			}
		}
	}

}
