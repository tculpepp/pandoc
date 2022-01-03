---
title: Exception Handling and File Processing
subtitle: Exception Handling and File Processing
author: Thomas Culpepper                      
institute: Trident University International
course: CSC310
assignment: Module 1 Case
---


Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nullam in tellus ornare libero elementum bibendum a sit amet magna. Vestibulum eu ex vitae odio hendrerit hendrerit. Integer aliquet, nisi non hendrerit porta, dui eros laoreet velit, sit amet finibus justo risus sit amet tortor. Mauris at sapien libero. Vestibulum eleifend purus quis elit pulvinar fermentum id id massa. Proin tincidunt nisi a vehicula rhoncus. Nullam ornare pretium accumsan. Pellentesque sollicitudin augue lorem, sit amet vulputate nunc dictum sed. Maecenas in feugiat felis, et facilisis enim. Etiam interdum, elit sit amet interdum commodo, dolor eros suscipit orci, vitae porta massa nunc nec odio. Vivamus quis arcu erat. Sed lorem lacus, scelerisque quis facilisis ac, volutpat vitae ante. Nulla tellus mi, aliquet ut laoreet ut, lobortis cursus nunc. In et facilisis mi, sodales finibus mauris. Cras a nisi suscipit quam accumsan dapibus in sed tortor. Sed gravida nibh justo, eu mattis lectus semper ornare.

Quisque viverra ex vitae lorem dictum, at facilisis odio tempus. Proin libero risus, gravida et bibendum eget, ornare sit amet mi. Phasellus vitae suscipit augue. Etiam iaculis mauris in suscipit interdum. Sed at nisl dolor. Ut ut sollicitudin tortor, eget porttitor erat. Vestibulum viverra ac nibh sit amet pretium. Ut commodo scelerisque neque tempor eleifend. Nulla facilisi. In mollis est quis urna efficitur, id porta leo maximus. Ut vel augue enim. Aliquam non odio pharetra lorem gravida facilisis.

~~~~~{#mycode .java .numberLines startFrom="100"}
import javax.swing.JOptionPane;
import java.util.regex.*;

public class CalcTaxes {
    public static void main(String[] args) {
        boolean calcAgain = true; //control to run again or exit

        JOptionPane.showMessageDialog(
            null, "This program will calculate your federal and state taxes");

        while (calcAgain) {
            String validationPattern = null;
            String errorMessage = null;
            String [] userInputs = new String[4]; //array to hold user input strings
            String [][] inputRequests = { //input requests and expected type (num or str)
                {"Please enter your name:","str"},
                {"Enter your yearly income","num"},
                {"Enter your Federal tax rate (%):","num"},
                {"Enter your State tax rate (%):","num"}
            };
~~~~~

Donec dui nunc, convallis nec lectus non, accumsan dictum lorem. Nam viverra, libero sed pulvinar tincidunt, mi augue rhoncus neque, et venenatis turpis velit quis odio. Nulla feugiat vitae urna id congue. Pellentesque efficitur facilisis hendrerit. Quisque vehicula vel risus vel faucibus. Quisque eleifend mattis maximus. Interdum et malesuada fames ac ante ipsum primis in faucibus.

Mauris blandit nisi non dapibus lobortis. Morbi sit amet elementum libero, sed laoreet est. Sed auctor nibh ac semper faucibus. Fusce pretium ultrices neque, sit amet luctus mi sollicitudin vel. Suspendisse efficitur metus quis dui posuere, id vehicula dui pulvinar. Donec sit amet dapibus diam. Donec libero sem, fringilla et cursus ut, lacinia quis nisl. Donec ullamcorper malesuada purus tempor venenatis. Morbi vel ante vulputate, feugiat velit at, pellentesque odio. Phasellus nec justo aliquet, maximus quam a, venenatis ligula. Ut porttitor metus id diam sollicitudin, non lacinia augue faucibus.

Morbi quis lobortis neque. Aenean blandit, dui et sollicitudin ullamcorper, neque leo rhoncus libero, vitae ullamcorper ex massa vitae dolor. Nam placerat posuere nulla ac consectetur. In porta ornare nisi quis suscipit. Quisque sed turpis sit amet mi sagittis molestie ac in nisi. Integer ligula nulla, lobortis ac elementum sit amet, ultricies eget leo. Nulla ullamcorper dolor vel neque pretium, quis porttitor est consequat. Donec euismod mauris sit amet dui fermentum, eget tempor dui suscipit. Ut eros risus, semper in sollicitudin vel, lacinia a sapien. Duis fermentum mauris nec diam vestibulum fringilla.

~~~~~{#mycodemore .java .numberLines startFrom="100"}
            for (int i=0; i < inputRequests.length; i++) {
                userInputs[i] = JOptionPane.showInputDialog(inputRequests[i][0]);
                if (userInputs[i] == null) { // Exit cleanly if user hits cancel
                    System.exit(0);
                }
                else if (inputRequests[i][1].equals("num")){
                    validationPattern = "^\\d+$|^-?\\d*\\.\\d{2}$"; // match integer or 2 place decimal
                    errorMessage = "Please enter a number \n(000 or 00.00)";
                }
                else if (inputRequests[i][1].equals("str")) {
                    validationPattern = "^[A-Za-z]+\\s*[A-Za-z]*$"; // match name and optional 2nd name
                    errorMessage = "Try again./nNo numbers or symbols please";
                }
                else {
                    JOptionPane.showMessageDialog(
                        null, "Illegal Input type Option. Please contact the developer.");
                    throw new IllegalArgumentException(
                        "Input type option invalid. Only 'num' or 'str' allowed");
                }

                Pattern p = Pattern.compile(validationPattern);
                Matcher m = p.matcher(userInputs[i]);
                if (!m.find()){ 
                    JOptionPane.showMessageDialog(null, errorMessage);
                    i--;
                }
            }

            double yearlyIncome = Double.parseDouble(userInputs[1]);
            double fedTaxRate = Double.parseDouble(userInputs[2]) / 100;
            double stateTaxRate = Double.parseDouble(userInputs[3]) / 100;
            double fedTaxDue = yearlyIncome * fedTaxRate;
            double stateTaxDue = yearlyIncome * stateTaxRate;

            JOptionPane.showMessageDialog(null, userInputs[0] + "\nYour Federal Taxes are: $" 
                + fedTaxDue + "\nYour State taxes are: $" + stateTaxDue);

            int reply = JOptionPane.showConfirmDialog(null, "Would you like to calculate more?", 
                "Run Again?",  JOptionPane.YES_NO_OPTION);
            if (reply == JOptionPane.NO_OPTION) {
                    calcAgain = false;
            }
        }
    } 
}
~~~~~

Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nullam in tellus ornare libero elementum bibendum a sit amet magna. Vestibulum eu ex vitae odio hendrerit hendrerit. Integer aliquet, nisi non hendrerit porta, dui eros laoreet velit, sit amet finibus justo risus sit amet tortor. Mauris at sapien libero. Vestibulum eleifend purus quis elit pulvinar fermentum id id massa. Proin tincidunt nisi a vehicula rhoncus. Nullam ornare pretium accumsan. Pellentesque sollicitudin augue lorem, sit amet vulputate nunc dictum sed. Maecenas in feugiat felis, et facilisis enim. Etiam interdum, elit sit amet interdum commodo, dolor eros suscipit orci, vitae porta massa nunc nec odio. Vivamus quis arcu erat. Sed lorem lacus, scelerisque quis facilisis ac, volutpat vitae ante. Nulla tellus mi, aliquet ut laoreet ut, lobortis cursus nunc. In et facilisis mi, sodales finibus mauris. Cras a nisi suscipit quam accumsan dapibus in sed tortor. Sed gravida nibh justo, eu mattis lectus semper ornare.

Quisque viverra ex vitae lorem dictum, at facilisis odio tempus. Proin libero risus, gravida et bibendum eget, ornare sit amet mi. Phasellus vitae suscipit augue. Etiam iaculis mauris in suscipit interdum. Sed at nisl dolor. Ut ut sollicitudin tortor, eget porttitor erat. Vestibulum viverra ac nibh sit amet pretium. Ut commodo scelerisque neque tempor eleifend. Nulla facilisi. In mollis est quis urna efficitur, id porta leo maximus. Ut vel augue enim. Aliquam non odio pharetra lorem gravida facilisis.

Donec dui nunc, convallis nec lectus non, accumsan dictum lorem. Nam viverra, libero sed pulvinar tincidunt, mi augue rhoncus neque, et venenatis turpis velit quis odio. Nulla feugiat vitae urna id congue. Pellentesque efficitur facilisis hendrerit. Quisque vehicula vel risus vel faucibus. Quisque eleifend mattis maximus. Interdum et malesuada fames ac ante ipsum primis in faucibus.

Mauris blandit nisi non dapibus lobortis. Morbi sit amet elementum libero, sed laoreet est. Sed auctor nibh ac semper faucibus. Fusce pretium ultrices neque, sit amet luctus mi sollicitudin vel. Suspendisse efficitur metus quis dui posuere, id vehicula dui pulvinar. Donec sit amet dapibus diam. Donec libero sem, fringilla et cursus ut, lacinia quis nisl. Donec ullamcorper malesuada purus tempor venenatis. Morbi vel ante vulputate, feugiat velit at, pellentesque odio. Phasellus nec justo aliquet, maximus quam a, venenatis ligula. Ut porttitor metus id diam sollicitudin, non lacinia augue faucibus.

Morbi quis lobortis neque. Aenean blandit, dui et sollicitudin ullamcorper, neque leo rhoncus libero, vitae ullamcorper ex massa vitae dolor. Nam placerat posuere nulla ac consectetur. In porta ornare nisi quis suscipit. Quisque sed turpis sit amet mi sagittis molestie ac in nisi. Integer ligula nulla, lobortis ac elementum sit amet, ultricies eget leo. Nulla ullamcorper dolor vel neque pretium, quis porttitor est consequat. Donec euismod mauris sit amet dui fermentum, eget tempor dui suscipit. Ut eros risus, semper in sollicitudin vel, lacinia a sapien. Duis fermentum mauris nec diam vestibulum fringilla.


![CalcTaxes Screen 1](media/CSC310-Case1-1.png){#fig:screen1 height=1.5in}


## References
