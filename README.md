# GUI
import javax.swing.*;
import java.awt.*;
import java.awt.event.*;

public class GUIExample3 extends JFrame {
	
	private JTextField textField1 = null;
	private JTextField textField2 = null;
	private JLabel label1 = null;
	private JLabel label2 = null;
	GridBagConstraints layoutConstraints = null;
	JButton button1 = null;
	JButton button2 = null;
	
	public GUIExample3() {
		
		this.setLayout(new GridBagLayout());
		label1 = new JLabel("Counter");
		layoutConstraints = new GridBagConstraints();
		layoutConstraints.gridx = 0;
		layoutConstraints.gridy = 0;
		layoutConstraints.insets = new Insets(10, 10, 10, 10);
		this.add(label1, layoutConstraints);
		
		textField1 = new JTextField(15);
		textField1.setText("0");
		layoutConstraints = new GridBagConstraints();
		layoutConstraints.gridx = 1;
		layoutConstraints.gridy = 0;
		layoutConstraints.insets = new Insets(10, 10, 10, 10);
		this.add(textField1, layoutConstraints);
		

		button1 = new JButton("Increment");
		layoutConstraints = new GridBagConstraints();
		layoutConstraints.gridx = 2;
		layoutConstraints.gridy = 0;
		layoutConstraints.insets = new Insets(10, 10, 10, 10);
		button1.addActionListener(new ActionListener() {
			@Override
			public void actionPerformed(ActionEvent e) {
				
				int val = Integer.parseInt(textField1.getText());
				textField1.setText(Integer.toString(val +1));
			}
		});
		this.add(button1, layoutConstraints);
		
		button2 = new JButton("Reset");
		layoutConstraints = new GridBagConstraints();
		layoutConstraints.gridx = 0;
		layoutConstraints.gridy = 2;
		layoutConstraints.insets = new Insets(10, 10, 10, 10);
		button2.addActionListener(new ActionListener() {
			public void actionPerformed(ActionEvent e) {
				textField1.setText("0");
				textField1.setText("");
			}
		});
		this.add(button2, layoutConstraints);
	}

	public static void main(String[] args) {
		
		GUIExample3 frame = new GUIExample3();
		
		frame.pack();
		frame.setVisible(true);
		frame.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
	}
}
