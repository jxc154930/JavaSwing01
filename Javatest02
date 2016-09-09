import javafx.scene.control.TextFormatter;

import javax.swing.*;
import javax.swing.border.*;
import javax.swing.event.ChangeEvent;
import javax.swing.event.ChangeListener;
import java.awt.event.ActionEvent;
import java.awt.event.ActionListener;

public class Javatest02 extends JFrame{

  public static void main(String[] args){
    new Javatest02();
  }

    JTextArea textArea01;
    JLabel label01, label02;
    JTextField textField01, textField02;
    JButton button01, button02;
    JSlider slider01;
    JCheckBox checkBox01, checkBox02;
    JRadioButton radioButton01, radioButton02, radioButton03, radioButton04;

    double num01, num02, totalCalc;

    public Javatest02(){

        JPanel panel01 = new JPanel();
        JPanel panel02 = new JPanel();


        textArea01 = new JTextArea(10, 10);
        textArea01.setWrapStyleWord(true);
        textArea01.setLineWrap(true);

        label01 = new JLabel("Results: ");
        label02 = new JLabel("Perform this many times: 1");

        textField01 = new JTextField(15);
        textField02 = new JTextField(15);

        button01 = new JButton("Calc");
        ListenForButton listenButton01 = new ListenForButton();
        button01.addActionListener(listenButton01);
        button02 = new JButton("Clear");
        ListenForButton01 listenButton02 = new ListenForButton01();
        button02.addActionListener(listenButton02);

        slider01 = new JSlider(0, 100, 1);
        slider01.setMinorTickSpacing(1);
        slider01.setMajorTickSpacing(10);
        slider01.setPaintLabels(true);
        slider01.setPaintTicks(true);
        ListenForSlider listenSlider01 = new ListenForSlider();
        slider01.addChangeListener(listenSlider01);

        checkBox01 = new JCheckBox();
        checkBox02 = new JCheckBox();
        checkBox02.setSelected(true);

        radioButton01 = new JRadioButton("Radio01");
        radioButton02 = new JRadioButton("Radio02");
        radioButton03 = new JRadioButton("Radio03");
        radioButton04 = new JRadioButton("Radio04");
        panel02.add(radioButton01);
        panel02.add(radioButton02);
        panel02.add(radioButton03);
        panel02.add(radioButton04);
        radioButton04.setSelected(true);

        ButtonGroup buttonGroup01 = new ButtonGroup();
        buttonGroup01.add(radioButton01);
        buttonGroup01.add(radioButton02);
        buttonGroup01.add(radioButton03);
        buttonGroup01.add(radioButton04);

        Border border01 = BorderFactory.createTitledBorder("buttonGroup01");
        panel02.setBorder(border01);

        panel01.add(panel02);
        panel01.add(textField01);
        panel01.add(textField02);
        panel01.add(button01);
        panel01.add(checkBox01);
        panel01.add(checkBox02);
        panel01.add(label02);
        panel01.add(slider01);
        panel01.add(label01);
        panel01.add(button02);
        panel01.add(textArea01);

        //JScrollPane scrollPane01 = new JScrollPane(textArea01, JScrollPane.VERTICAL_SCROLLBAR_AS_NEEDED, JScrollPane.HORIZONTAL_SCROLLBAR_AS_NEEDED);
        //this.add(scrollPane01);

        checkBox01.requestFocus();
        this.setTitle("Javatest02");
        this.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
        this.setSize(480, 480);
        this.setLocationRelativeTo(null);
        this.add(panel01);
        this.setVisible(true);
    }
    private class ListenForButton implements ActionListener{
        @Override
        public void actionPerformed(ActionEvent e) {
            if(e.getSource() == button01){
                try{
                    num01 = Double.parseDouble(textField01.getText());
                    num02 = Double.parseDouble(textField02.getText());
                }catch(NumberFormatException except){
                    JOptionPane.showMessageDialog(Javatest02.this, "Enter only numbers", "ErrorMsg", JOptionPane.ERROR_MESSAGE);
                    //System.exit(0);
                }
                if(radioButton01.isSelected()){
                    totalCalc = addNumbers(num01, num02, slider01.getValue());
                }else if(radioButton02.isSelected()){
                    totalCalc = subNumbers(num01, num02, slider01.getValue());
                }else if(radioButton01.isSelected()){
                    totalCalc = mulNumbers(num01, num02, slider01.getValue());
                }else if(radioButton04.isSelected()){
                    totalCalc = divNumbers(num01, num02, slider01.getValue());
                }

                if(checkBox01.isSelected()){
                    textArea01.append("Check01: " + totalCalc + "\n");
                }else if(checkBox02.isSelected()){
                    textArea01.append("Check02: " + totalCalc + "\n");
                }else{
                    textArea01.append("nullCheck: " + totalCalc + "\n");
                }
            }
        }
    }
    private class ListenForButton01 implements ActionListener{
        @Override
        public void actionPerformed(ActionEvent e) {
            if (e.getSource() == button02){
                textArea01.setText("");

            }
        }
    }

    private class ListenForSlider implements ChangeListener{
        @Override
        public void stateChanged(ChangeEvent e) {
            if(e.getSource() == slider01){
                label02.setText("Perform this many times:" + slider01.getValue());
            }
        }
    }
    public static double addNumbers(double number01, double number02, double slider){
        double result =0;
        for(int i=0; i< slider; i++){
            result += number01 + number02;
        }
        return result;
    }
    public static double subNumbers(double number01, double number02, double slider){
        double result =0;
        for(int i=0; i<slider; i++){
            result += number01 - number02;
        }
        return result;
    }
    public static double mulNumbers(double number01, double number02, double slider){
        double result =0;
        for(int i=0; i<slider; i++){
            result += number01 * number02;
        }
        return result;
    }
    public static double divNumbers(double number01, double number02, double slider){
        double result =0;
        for(int i=0; i<slider; i++){
            result += number01 / number02;
        }
        return result;
    }

}
