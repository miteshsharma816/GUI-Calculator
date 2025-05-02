# GUI-Calculator
import javax.swing.*;
import java.awt.event.*;

public class SimpleCalculator {

    public static void main(String[] args) {
        // Create frame
        JFrame frame = new JFrame("Simple Calculator");
        frame.setSize(300, 250);
        frame.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
        frame.setLayout(null);

        // Create components
        JLabel label1 = new JLabel("Number 1:");
        label1.setBounds(20, 20, 80, 25);
        frame.add(label1);

        JTextField text1 = new JTextField();
        text1.setBounds(100, 20, 150, 25);
        frame.add(text1);

        JLabel label2 = new JLabel("Number 2:");
        label2.setBounds(20, 60, 80, 25);
        frame.add(label2);

        JTextField text2 = new JTextField();
        text2.setBounds(100, 60, 150, 25);
        frame.add(text2);

        JButton addButton = new JButton("Add");
        addButton.setBounds(20, 100, 100, 30);
        frame.add(addButton);

        JButton subButton = new JButton("Subtract");
        subButton.setBounds(150, 100, 100, 30);
        frame.add(subButton);

        JButton mulButton = new JButton("Multiply");
        mulButton.setBounds(20, 140, 100, 30);
        frame.add(mulButton);

        JButton divButton = new JButton("Divide");
        divButton.setBounds(150, 140, 100, 30);
        frame.add(divButton);

        JLabel resultLabel = new JLabel("Result: ");
        resultLabel.setBounds(20, 180, 250, 25);
        frame.add(resultLabel);

        // Add Action Listeners
        addButton.addActionListener(e -> {
            int num1 = Integer.parseInt(text1.getText());
            int num2 = Integer.parseInt(text2.getText());
            int result = num1 + num2;
            resultLabel.setText("Result: " + result);
        });

        subButton.addActionListener(e -> {
            int num1 = Integer.parseInt(text1.getText());
            int num2 = Integer.parseInt(text2.getText());
            int result = num1 - num2;
            resultLabel.setText("Result: " + result);
        });

        mulButton.addActionListener(e -> {
            int num1 = Integer.parseInt(text1.getText());
            int num2 = Integer.parseInt(text2.getText());
            int result = num1 * num2;
            resultLabel.setText("Result: " + result);
        });

        divButton.addActionListener(e -> {
            int num1 = Integer.parseInt(text1.getText());
            int num2 = Integer.parseInt(text2.getText());
            if (num2 != 0) {
                double result = (double) num1 / num2;
                resultLabel.setText("Result: " + result);
            } else {
                resultLabel.setText("Result: Cannot divide by 0");
            }
        });

        // Make frame visible
        frame.setVisible(true);
    }
}
