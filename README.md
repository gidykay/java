import javax.swing.*;
import java.awt.*;
import java.awt.event.ActionEvent;
import java.awt.event.ActionListener;

public class PetApp {
    public static void main(String[] args) {
        SwingUtilities.invokeLater(() -> createAndShowGUI());
    }

    private static void createAndShowGUI() {
        JFrame frame = new JFrame("Pet App");
        frame.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);

        JPanel panel = new JPanel();
        panel.setLayout(new BoxLayout(panel, BoxLayout.Y_AXIS));

        JLabel label = new JLabel("Choose a pet:");
        panel.add(label);

        ButtonGroup group = new ButtonGroup();

        JRadioButton butRadio = new JRadioButton("Butterfly");
        group.add(butRadio);
        panel.add(butRadio);

        JRadioButton birdRadio = new JRadioButton("Bird");
        group.add(birdRadio);
        panel.add(birdRadio);

        JRadioButton dogRadio = new JRadioButton("Dog");
        group.add(dogRadio);
        panel.add(dogRadio);

        JRadioButton catRadio = new JRadioButton("Cat");
        group.add(catRadio);
        panel.add(catRadio);

        JRadioButton rabbitRadio = new JRadioButton("Rabbit");
        group.add(rabbitRadio);
        panel.add(rabbitRadio);

        JRadioButton pigRadio = new JRadioButton("Pig");
        group.add(pigRadio);
        panel.add(pigRadio);

        butRadio.setSelected(true);

        ActionListener listener = e -> {
            if (butRadio.isSelected()) {
                label.setText("Butterfly is selected.");
            } else if (birdRadio.isSelected()) {
                label.setText("Bird is selected.");
            } else if (dogRadio.isSelected()) {
                label.setText("Dog is selected.");
            } else if (catRadio.isSelected()) {
                label.setText("Cat is selected.");
            } else if (rabbitRadio.isSelected()) {
                label.setText("Rabbit is selected.");
            } else if (pigRadio.isSelected()) {
                label.setText("Pig is selected.");
            }
        };

        butRadio.addActionListener(listener);
        birdRadio.addActionListener(listener);
        dogRadio.addActionListener(listener);
        catRadio.addActionListener(listener);
        rabbitRadio.addActionListener(listener);
        pigRadio.addActionListener(listener);

        frame.add(panel, BorderLayout.CENTER);
        frame.pack();
        frame.setVisible(true);
    }
}
