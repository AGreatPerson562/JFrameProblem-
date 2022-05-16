# JFrameProblem-
//This is the class where i put my code(the first class)
import sun.font.FontStrike;

import javax.swing.*;
import java.awt.*;

import java.io.*;

public class Form extends JFrame {
    public void setTitle(String str){
        super.setTitle(str);
    }
    public String getTitle(){
        return super.getTitle();
    }
    public void setSize(Dimension dimension){
        super.setSize(dimension);
    }
    public Dimension getSize(){
        return super.getSize();
    }
    public void setLocation(Point p) {
        super.setLocation(p);
    }
    public void addComp(Component c){
        super.add(c);
    }

    JButton btnsignup = new JButton();
    JButton btnlogin = new JButton();
    public Form(){
        try{ 
            Color c = Color.WHITE;
            Form f = this;
            f.getContentPane().setBackground(new Color(90,70,120));
            f.setTitle("");
            f.setLayout(null);
            f.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
            f.setSize(new Dimension(1000,750));
            f.setLocation(new Point(30,30));
            f.setResizable(false);
            ImageIcon i = new ImageIcon("E:\\Downloads\\ZantroSpearow.png");
            Image image;
            f.setIconImage(i.getImage());
            btnsignup.setBounds(40,780-60-10,100,60);
            btnsignup.setName("Sign up");
            btnsignup.setBackground(Color.BLUE);
            btnsignup.setFont(new Font("Arial",12,14));
            btnsignup.setForeground(c);
            btnlogin.setBounds(150,780-60-10,100,60);
            btnlogin.setName("Log in");
            btnlogin.setBackground(Color.BLUE);
            btnlogin.setForeground(c);
            btnsignup.addActionListener(x->
            {
                try{
                File fl = new File("ManyThings.txt");
                if(fl.exists()) {
                    FileWriter fw = new FileWriter("ManyThings.txt");
                    fw.write("Hey, I am a peace of crap");
                    fw.close();
                }
            }catch (Exception e){
                    JOptionPane.showMessageDialog(null,e);
                }

            });
            btnlogin.addActionListener(l ->
            {

            });
            f.setVisible(true);
            f.addComp(btnsignup);
            f.addComp(btnlogin);
            btnsignup.setVisible(true);
            btnlogin.setVisible(true);
        }
        catch(Exception e){
            JOptionPane.showMessageDialog(null, e);
        }
    }
}
//The main class:
new Form();
