---
title: Как создать службу рабочих процессов, которая вызывает другую службу рабочих процессов
ms.date: 03/30/2017
ms.assetid: 99b3ee3e-aeb7-4e6f-8321-60fe6140eb67
ms.openlocfilehash: 1b30da34f7c85cccd98b18cd32b81c83630989b2
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/05/2018
ms.locfileid: "43725063"
---
# <a name="how-to-create-a-workflow-service-that-calls-another-workflow-service"></a>Как создать службу рабочих процессов, которая вызывает другую службу рабочих процессов

Иногда службе рабочего процесса требуется получить данные от другой службы рабочего процесса. В этом разделе описывается, как вызвать одну службу рабочего процесса из другой. В этом разделе мы создадим две службы рабочего процесса (одну с методом, который обращает входную строку, и вторую, которая преобразует входную строку в верхний регистр после обращения строки, которая использует первую службу).

### <a name="to-create-the-reverser-workflow-service"></a>Создание службы рабочего процесса Reverser

1.  Запустите Visual Studio.

2.  Выберите **файл** > **новый проект**. В разделе **рабочего процесса** узел в **установленные шаблоны** области выберите **приложение службы рабочего процесса WCF**. Назовите решение `NestedServices` и нажмите кнопку **ОК**.

3.  В разделе **серверы**, убедитесь, что **использовать локальный веб-сервер IIS** выбран. Нажмите кнопку **создать виртуальный каталог**. Нажмите кнопку **ОК** в диалоговое окно с предупреждением, виртуальный каталог был успешно создан.

4.  В обозревателе решений переименуйте файл Service1.xamlx в `StringReverserService.xamlx`.

5.  На **свойства проекта** для нового проекта и щелкните **Web** вкладки. Задайте **действие при запуске** для **определенную страницу**и выберите StringReverserService.xamlx в качестве стартовой страницы.

6.  Откройте файл StringReverserService.xamlx в конструкторе и удалите существующие действия `ReceiveRequest` и `SendReply`, затем перетащите действие `ReceiveAndSendReply` в существующее действие последовательности.

    1.  Задайте **Имя_операции** задайте значение ReverseString.

    2.  Задайте **ServiceContractName** задайте значение IReverseString.

    3.  Выберите **CanCreateInstance** "флажок".

7.  Выберите **SequentialService** действия, а затем щелкните **переменных** вкладку в нижней части конструктора. Создайте две новые переменные типа String с именами StringToReverse и ReversedStringToReturn.

8.  Нажмите кнопку **определить** ссылку в **Receive** действия. Нажмите кнопку **параметры**и создайте параметр с именем InputString, назначенный StringToReverse строкового типа.

9. Нажмите кнопку **определить** ссылку в **SendReplyToReceive** действия. Нажмите кнопку **параметры**и создайте параметр с именем ReversedString типа String, назначенный ReversedStringToReturn.

10. Чтобы реализовать логику для службы, создайте в проекте новый класс с именем StringLibrary.  Замените определение класса на следующий код.

    ```
    public class StringLibrary
        {
            public static String ReverseString(string StringToReverse)
            {
                char[] charArray = StringToReverse.ToCharArray();
                Array.Reverse(charArray);
                return new String(charArray);
            }
        }
    ```

11. Чтобы вызвать метод reversestring при вводе, перетащите **InvokeMethod** действия из области элементов в пространство между **Receive** и **SendReply** действий. Установите свойства действия следующим образом.

    1.  **Имя_метода**: значение ReverseString

    2.  **Результат**: ReversedStringToReturn

    3.  **Параметры**: создайте новый параметр, где **направление** имеет значение In, **тип** строки и **значение** ― StringToReverse.

    4.  **TargetType**: NestedServices.StringLibrary

12. Проверьте службу, нажав клавишу F5. В открывшемся клиенте теста WCF дважды щелкните метод ReverseString(). В области запросов введите `Sample` для значения параметра InputString. Нажмите кнопку **вызова**. Служба должна вернуть «elpmaS».

### <a name="to-create-the-uppercaser-workflow-service"></a>Создание службы рабочего процесса UpperCaser

1.  Щелкните проект NestedServices правой кнопкой мыши и выберите **добавить** > **новый элемент**. В **рабочего процесса** выберите **службы WCF Workflow Service**и присвойте имя новой службы `UpperCaserService`. Нажмите кнопку **Добавить**. После этого в проект должна будет быть добавлена новая служба рабочего процесса с именем UpperCaserService.xamlx.

2.  Откройте файл UpperCaserService.xamlx в конструкторе и удалите существующие **ReceiveRequest** и `SendReply` , после чего перетащите `ReceiveAndSendReply` действия в существующее действие последовательности.

    1.  Задайте **Имя_операции** задайте значение UpperCaseString.

    2.  Задайте **ServiceContractName** задайте значение IUpperCaseString.

    3.  Выберите **CanCreateInstance** "флажок".

3.  Выберите действие SequentialService, затем нажмите кнопку **переменных** вкладку в нижней части конструктора. Создайте три новые переменные типа String с именами StringToUpper, StringToReverse и StringToReturn.

4.  Нажмите кнопку **определить** ссылку в **Receive** действия. Нажмите кнопку **параметры**и создайте параметр с именем InputString, назначенный StringToUpper строкового типа.

5.  Нажмите кнопку **определить** ссылку в **SendReplyToReceive** действия. Нажмите кнопку **параметры**и создайте параметр с именем ModifiedString типа String, назначенный StringToReturn.

6.  Чтобы реализовать логику для службы, создайте в проекте с помощью следующего кода новый метод в классе StringLibrary.

    ```
    public static String UpperCaseString(string StringToUpperCase)
    {
         return StringToUpperCase.ToUpper();

    }
    ```

7.  Чтобы вызвать метод uppercasestring при вводе, перетащите **InvokeMethod** действия из области элементов в пространство между **Receive** и **SendReply** действий. Установите свойства действия следующим образом.

    1.  **Имя_метода**: значение UpperCaseString

    2.  **Результат**: StringToReverse

    3.  **Параметры**: создайте новый параметр, где **направление** имеет значение In, **тип** строки и **значение** ― StringToUpper.

    4.  **TargetType**: NestedServices.StringLibrary

8.  Теперь для измененной строки мы вызовем первую службу. Щелкните правой кнопкой мыши проект и выберите **добавить** > **ссылки на службу**. Добавьте ссылку на службу http://localhost/NestedServices/StringReverserService.xamlx и постройте проект, чтобы создать настраиваемое действие для доступа к первой веб-службе.

9. Перетащите экземпляр нового действия рабочего процесса, между **InvokeMethod** действия и **SendReplyToReceive** действий. Назначьте переменную StringToReverse свойству InputString нового действия, а переменную StringToReturn ― свойству StringToReturn.

10. Откройте страницу свойств для проекта NestedServices и измените **определенную страницу** в **Web** вкладке значение uppercaserservice.xamlx.

11. Проверьте службу, нажав клавишу F5. В открывшемся клиенте теста WCF дважды щелкните метод ReverseString(). В области запросов введите `Sample` для значения параметра InputString. Нажмите кнопку **вызова**. Служба должна вернуть «ELPMAS».

### <a name="to-create-a-client-to-call-the-services"></a>Создание клиента для вызова служб

1.  Добавьте в решение новый проект консольного приложения с именем Client.

2.  Щелкните правой кнопкой мыши клиентский проект и выберите **добавить** > **ссылки на службу**. В открывшемся окне щелкните **Discover**. Выберите StringReverserService.xamlx и в качестве пространства имен введите ReverseService.  Нажмите кнопку **ОК**.

3.  Замените метод Main в файле Program.cs следующим кодом.

    ```
    static void Main(string[] args)
    {
        Console.Write("Input string to process:");
        String input = Console.ReadLine();
        var service = new ReverseService.ReverseStringClient();
        Console.WriteLine("Output from service: {0}", service.ReverseString(input));
        Console.ReadKey();
    }
    ```