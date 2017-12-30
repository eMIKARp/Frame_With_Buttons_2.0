# Frame_With_Buttons_2.0
a piece of code that displays a frame with few buttons on it which change bacground color of the frame after cliciking them
  
    package eventhandling;

    import javax.swing.*;
    import java.awt.*;
    import java.awt.event.*;

    public class Main extends JFrame {

    public Main()
    {
        super("Buttons that change background color");
        this.setIconImage(Toolkit.getDefaultToolkit().getImage("image.png"));
        this.setBounds(300,300,500,300);
        initComponents();
        this.pack();
        this.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
    }
    
    public void initComponents()
    {
        kolorCzerwony = new JButton("Czerwony");
        kolorNiebieski = new JButton("Niebieski");
        kolorZielony = new JButton("Zielony");
        kolorZolty = new JButton("Żółty");
        kolorRozowy = new JButton("Różowy");
        
        kolorCzerwony.addActionListener(new colorListener(Color.RED));
        kolorNiebieski.addActionListener(new colorListener(Color.BLUE));
        kolorZielony.addActionListener(new colorListener(Color.GREEN));
        kolorZolty.addActionListener(new colorListener(Color.YELLOW));
        kolorRozowy.addActionListener(new colorListener(Color.PINK));
       
        panel.add(kolorCzerwony);
        panel.add(kolorNiebieski);
        panel.add(kolorZielony);
        panel.add(kolorZolty);
        panel.add(kolorRozowy);
        
        budujButton("Szary", Color.GRAY);
        
        this.getContentPane().add(panel);
    }
    
    JPanel panel = new JPanel();
    JButton kolorCzerwony;
    JButton kolorNiebieski;
    JButton kolorZielony;
    JButton kolorZolty;
    JButton kolorRozowy;
    
    
    public void budujButton(String nazwa, Color color)
    {
        
        JButton button = new JButton(nazwa);
        button.addActionListener(new colorListener(color));
        panel.add(button);
    }
    
    
    private class colorListener implements ActionListener
    {
        public colorListener(Color color)
        {
            this.color = color;
        }

        @Override
        public void actionPerformed(ActionEvent e) 
        {
            
            panel.setBackground(color);
            
        }
        
        Color color;
        
    }
    
    public static void main(String[] args) {
        
        new Main().setVisible(true);
        
    }
    
    }
