# Java_formatting
**Форматирование строк и чисел в Java**

Форматированный вывод в Java
*В Java существует два основных способа форматированного вывода:

System.out.printf() - для прямого вывода в консоль
String.format() - для создания форматированной строки

Основные спецификаторы формата
%s - для строк
%d - для целых чисел
%f - для чисел с плавающей точкой
%x - для шестнадцатеричных чисел
Примеры использования
Вывод строк:

String name = "Сергей";
System.out.printf("Привет, %s!", name);

                  
Вывод чисел:

int x = 10, y = 5;
int result = x + y;
System.out.printf("%d + %d = %d%n", x, y, result);

                  
Шестнадцатеричный формат:

int hex = 0xFF;
System.out.printf("Десятичное: %d, Шестнадцатеричное: %x%n", hex, hex);

                  
String.format()
Для сохранения форматированной строки в переменную используется метод String.format():

String output = String.format("%d + %d = %d", x, y, result);
System.out.println(output);

                  
Особенности
printf не делает автоматический перевод строки в отличие от println
Можно использовать несколько спецификаторов в одной строке
Весь код
public class Ex04FormattedOutput {
    public static void main(String[] args) {
        // System.out.printf(String format, Object... args);
        // - %s – строка
        // - %d – целое число
        // - %f – число с плавающей запятой
        // - %t – дата/время
        // - %x – шестнадцатеричное число

        // Привет, Имя!
        String name = "Сергей";
        // System.out.println("Привет, " + name + "!");
        System.out.printf("Привет, %s!\n", name);
        int x = 10;
        int y = 5;
        int result = x + y;
        String title = "Результат";
        System.out.println(title + ": " + x + " + " + y + " = " + result);
        System.out.printf("%s: %d + %d = %d\n", title, x, y, result);
        System.out.printf("%x\n", 0xff);

        String output = String.format(">> %s: %d + %d = %d\n", title, x, y, result);
        System.out.println(output);

    }
}

**Форматирование чисел в Java**

Форматированный вывод в Java предоставляет широкие возможности для красивого отображения числовых данных. Вот основные способы форматирования:

Числа с плавающей точкой
Базовое форматирование

double number = 123.456789;
String formatted = String.format("%.2f", number); // 123.46

                  
Спецификатор `.2f` указывает на вывод двух знаков после запятой с автоматическим округлением.

Выравнивание

// По левому краю
System.out.printf("|%-10d|", 123);  // |123        |

// По правому краю 
System.out.printf("|%10d|", 123);   // |       123|

                  
Дополнительные возможности
Ведущие нули

System.out.printf("|%010d|", 123);  // |0000000123|

                  
Разделители тысяч

int number = 10000000;
System.out.printf("%,d", number);    // 10,000,000

                  
Научная нотация

double number = 12345.6789;
System.out.printf("%e", number);     // 1.234568e+04

                  
Явное указание знака

int number = 123;
System.out.printf("%+d", number);    // +123
System.out.printf("|%+10d|", number); // |      +123|

                  
Класс DecimalFormat
Для более сложного форматирования можно использовать DecimalFormat:

DecimalFormat df = new DecimalFormat("0000.###");
System.out.println(df.format(42.224463)); // 0042.224
