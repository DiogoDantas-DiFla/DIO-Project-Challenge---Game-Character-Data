# Source Code

## GameCharacterData.java
import javax.swing.*;

public class GameCharacterData {

    private String heroName;
    private String heroAge;
    private int heroClass;

    private void setHeroName() {
        heroName = JOptionPane.showInputDialog("What is the name of the hero?");

        while (heroName.isBlank()) {
            JOptionPane.showMessageDialog(null, "Please, insert a name", "Empty Field", JOptionPane.ERROR_MESSAGE);
            heroName = JOptionPane.showInputDialog("What is the name of the hero?");
        }
    }

    private void setHeroAge() {
        heroAge = JOptionPane.showInputDialog("What is the age of the hero?");

        while (heroAge.isBlank() || !heroAge.matches("[0-9]+")) {
            JOptionPane.showMessageDialog(null, "Please, insert a non-empty number with no letters or negative numbers", "Invalid Input", JOptionPane.ERROR_MESSAGE);
            heroAge = JOptionPane.showInputDialog("What is the age of the hero?");
        }
    }

    private void setHeroClass() {
        String[] heroClassOptions = {"Warrior", "Mage", "Monk", "Ninja"};

        heroClass = JOptionPane.showOptionDialog(
                null, "Select one:", "Choose your hero Class", 0, 3, null, heroClassOptions, heroClassOptions[0]);
    }

    private void heroData(int classOfTheHero) {
        switch (classOfTheHero) {
            case 0:
                JOptionPane.showMessageDialog(
                        null, "The hero named " + heroName + " is a warrior," +
                                " he/she is " + heroAge + " years old and attacked with a sword");
                break;

            case 1:
                JOptionPane.showMessageDialog(
                        null, "The hero named " + heroName + " is a mage," +
                                " he/she is " + heroAge + " years old and attacked with a spell");
                break;

            case 2:
                JOptionPane.showMessageDialog(
                        null, "The hero named " + heroName + " is a monk,"  +
                                " he/she is " + heroAge + " years old and attacked using his/her hands and feet");
                break;

            case 3:
                JOptionPane.showMessageDialog(null, "The hero named " + heroName + " is a ninja," +
                        " he/she is " + heroAge + " years old and attacked with a shuriken");
                break;
        }
    }

    public void showHeroData() {
        setHeroName();
        setHeroAge();
        setHeroClass();
        heroData(heroClass);
    }

}



## Main.java
public class Main {

    public static void main(String[] args) {
        GameCharacterData heroData = new GameCharacterData();

        heroData.showHeroData();
    }

}



