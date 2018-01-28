# sasnazet
package cycles;

public class Snowflake {
    public static void main(String[] args) {
        int iLen = 10;
        char[][] arrSnow;
        arrSnow = makeSnowflake(iLen);
        showSnowflake(arrSnow);
    }

    private static char[][] makeSnowflake(int iLenght) {
        iLenght = ((iLenght >> 1) << 1) + 1;
        char[][]snow = new char[iLenght][iLenght];

        for (int i = 0; i <snow.length; i++) {
            for (int j = 0; j < snow.length; j++) {
                snow[i][j] = ' ';
            }
        }

        for (int i=0; i<iLenght; i++) {
            snow[i][i] = 'X';
            snow[i][iLenght - 1 - i] = 'X';
            snow[i][iLenght >>1] = 'X';
            snow[iLenght >>1][i] = 'X';
        }

        return snow;
    }

    private static void showSnowflake(char[][] snow) {
        for (char[] i : snow) {
            for (char j : i) {
                System.out.print(" " + j + " ");
            }
            System.out.println("");
        }
    }
}
