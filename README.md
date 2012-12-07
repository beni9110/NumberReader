//NumberReader
//============

/*
 * To change this template, choose Tools | Templates
 * and open the template in the editor.
 */
package numberreader;

import java.util.Scanner;

/**
 *
 * @author s504
 */
public class NumberReader {

    private int number;

    public void read() throws NumberFormatException, NegativeException {
        Scanner sc = new Scanner(System.in);
        System.out.println("Enter number");
        number = Integer.parseInt(sc.nextLine());

        if (number < 0) {
            throw new NegativeException();
        }
    }

    public int getNumber() {
        return number;
    }

    /**
     * @param args the command line arguments
     */
    public static void main(String[] args) {

        try {
            NumberReader nr = new NumberReader();
            nr.read();
            System.out.println(nr.getNumber());
        } catch (NumberFormatException nfe) {
            System.err.println("Enter the number");
        }
        
        catch (NegativeException nfe )
        {
            System.err.println("chisloto e po malko ot nula");
        }
    }
}
