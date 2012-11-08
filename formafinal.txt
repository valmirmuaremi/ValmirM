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

final JLabel position=new JLabel("Position");
position.setBounds(10,130,100,50);
comCon.add(position);

String [] positionList={"Goalkeeper","Defender","Midfielder","Attacker"};
final JComboBox combo3=new JComboBox(positionList);
combo3.setSelectedIndex(2);
combo3.setBounds(75, 145, 150, 20);
comCon.add(combo3);

final String [] footList={"The Player shots with Left foot","The Player shots with Right","The Player shots with Both foots"};
final JRadioButton buton=new JRadioButton(footList[0]);
final JRadioButton buton1=new JRadioButton(footList[1]);
final JRadioButton buton2=new JRadioButton(footList[2]);

buton.setActionCommand(footList[0]);
buton1.setActionCommand(footList[1]);
buton2.setActionCommand(footList[2]);

buton.setSelected(true);

buton.setBounds(20, 200, 250, 15);
buton1.setBounds(20, 220, 250, 15);
buton2.setBounds(20, 240, 250, 15);


comCon.add(buton);
comCon.add(buton1);
comCon.add(buton2);

ButtonGroup grupa=new ButtonGroup();
grupa.add(buton);
grupa.add(buton1);
grupa.add(buton2);

final JLabel height=new JLabel("Height");
height.setBounds(10,260,100,50);
comCon.add(height);

final JTextField height1=new JTextField();
height1.setBounds(75,275,150,20);
comCon.add(height1);

final JLabel weight=new JLabel("Weight");
weight.setBounds(10,290,100,50);
comCon.add(weight);

final JTextField weight1=new JTextField();
weight1.setBounds(75,305,150,20);
comCon.add(weight1);

final String [] fitList={"The Player is fit to play","The Player is injured"};
final JRadioButton kopce=new JRadioButton(fitList[0]);
final JRadioButton kopce1=new JRadioButton(fitList[1]);

kopce.setActionCommand(fitList[0]);
kopce1.setActionCommand(fitList[1]);

kopce.setSelected(true);

kopce.setBounds(20, 330, 250, 15);
kopce1.setBounds(20, 350, 250, 15);

comCon.add(kopce);
comCon.add(kopce1);

ButtonGroup grupa1=new ButtonGroup();
grupa1.add(kopce);
grupa1.add(kopce1);

JButton kop1=new JButton("Save");
kop1.setBounds(330, 380, 150, 20);
comCon.add(kop1);
kop1.setToolTipText("Save the info");

kop1.addActionListener(new ActionListener(){
@Override
public void actionPerformed(ActionEvent arg0) {
// TODO Auto-generated method stub
if(ime1.getText().equals("")||prezime1.getText().equals(""))
{
JOptionPane.showMessageDialog(comCon,"The fileds with (*) must be filled!","WARNING!", JOptionPane.WARNING_MESSAGE);

}
else{
try{
FileWriter record=new FileWriter("D:/record.txt");
BufferedWriter out=new BufferedWriter(record);
out.write("--------------USER INFO--------------"+"\r\n");
out.write("Name: "+ime1.getText()+"\r\n");
out.write("*: "+ime3.getText()+"\r\n");
out.write("Surname: "+prezime1.getText()+"\r\n");
out.write("*: "+ime4.getText()+"\r\n");
out.write("Date of Birth : "+combo1.getSelectedItem()+"\r\n");
out.write("Month of Birth: "+combo2.getSelectedItem()+"\r\n");
out.write("Position: "+combo3.getSelectedItem()+"\r\n");

if(buton.isSelected()){
out.write("Foot"+footList[0]+"\r\n");
}
if(buton1.isSelected()){
out.write("Foot"+footList[1]+"\r\n");
}
if(buton2.isSelected()){
out.write("Foot"+footList[2]+"\r\n");
}
out.write("Height: "+height1.getText()+"\r\n");
out.write("Weight: "+weight1.getText()+"\r\n");

if(kopce.isSelected()){
out.write("Fit"+fitList[0]+"\r\n");
}
if(kopce1.isSelected()){
out.write("Fit"+fitList[1]+"\r\n");
}

out.write("----------------------------------");
out.close();
JOptionPane.showMessageDialog(comCon, "saved");
}
catch(Exception e){

}}
}




});



}





}