import java.awt.event.ActionEvent;
import java.awt.event.ActionListener;
import java.io.BufferedWriter;
import java.io.FileWriter;

import javax.swing.ButtonGroup;
import javax.swing.JButton;
import javax.swing.JFrame;
import javax.swing.JLabel;
import javax.swing.JOptionPane;
import javax.swing.JPanel;
import javax.swing.JRadioButton;
import javax.swing.JTextField;
import javax.swing.JCheckBox;
import javax.swing.JComboBox;

public class PlayerInfo extends JFrame {

public PlayerInfo(){
setTitle("PlayerInfo");
setSize(800,600);
setLocationRelativeTo(null);

final JPanel comCon=new JPanel();
getContentPane().add(comCon);
comCon.setLayout(null);

final JLabel ime=new JLabel("Name");
ime.setBounds(10,10,100,50);
comCon.add(ime);

final JTextField ime1=new JTextField();
ime1.setBounds(75,25,150,20);
comCon.add(ime1);

final JLabel ime3=new JLabel("*");
ime3.setBounds(230,10,100,50);
comCon.add(ime3);

final JLabel prezime=new JLabel("Surname");
prezime.setBounds(10,50,100,50);
comCon.add(prezime);


final JTextField prezime1=new JTextField();
prezime1.setBounds(75,65,150,20);
comCon.add(prezime1);

final JLabel ime4=new JLabel("*");
ime4.setBounds(230,50,100,50);
comCon.add(ime4);

final JLabel date=new JLabel("Date of Birth");
date.setBounds(10,90,100,50);
comCon.add(date);

String [] dayList={"1","2","3","4","5","6","7","8","9","10","11","12","13","15","16","17","18","19","20","21","22","23","24","25","26","27","28","29","30","31"};
final JComboBox combo1=new JComboBox(dayList);
combo1.setSelectedIndex(2);
combo1.setBounds(85, 105, 150, 20);
comCon.add(combo1);

final JLabel month=new JLabel("Month of Birth");
month.setBounds(250,90,100,50);
comCon.add(month);

String [] monthList={"January","February","March","April","May","June","July","August","September","October","November","December"};
final JComboBox combo2=new JComboBox(monthList);
combo2.setSelectedIndex(2);
combo2.setBounds(340, 105, 150, 20);
comCon.add(combo2);

final JLabel year=new JLabel("Year of Birth");
year.setBounds(500,90,100,50);
comCon.add(year);

final JTextField year1=new JTextField();
year1.setBounds(580,105,150,20);
comCon.add(year1);



JButton kop1=new JButton("Save");
kop1.setBounds(330, 380, 150, 20);
comCon.add(kop1);
kop1.setToolTipText("Save the info");

}}