---
title: "Как создать службу рабочих процессов, которая вызывает другую службу рабочих процессов | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 99b3ee3e-aeb7-4e6f-8321-60fe6140eb67
caps.latest.revision: 7
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 7
---
# Как создать службу рабочих процессов, которая вызывает другую службу рабочих процессов
Иногда службе рабочего процесса требуется получить данные от другой службы рабочего процесса.В этом разделе описывается, как вызвать одну службу рабочего процесса из другой.В этом разделе мы создадим две службы рабочего процесса \(одну с методом, который обращает входную строку, и вторую, которая преобразует входную строку в верхний регистр после обращения строки, которая использует первую службу\).  
  
### Создание службы рабочего процесса Reverser  
  
1.  Запустите [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] от имени администратора.  
  
2.  Выберите **Файл**, **Создать проект**.В узле **Рабочий процесс** в области **Установленные шаблоны** выберите **Служебное приложение рабочего процесса WCF**.Присвойте решению имя `NestedServices` и нажмите кнопку **ОК**.  
  
3.  Откройте узел **Серверы** и удостоверьтесь, чтобы выбрано **Использовать локальный веб\-сервер IIS**.Нажмите **Создать виртуальный каталог**.В диалоговом окне с сообщением о том, что виртуальный каталог был успешно создан, нажмите кнопку **ОК**.  
  
4.  В обозревателе решений переименуйте файл Service1.xamlx в `StringReverserService.xamlx`.  
  
5.  На странице **Свойства проекта** для нового проекта перейдите на вкладку **Веб**.Параметру **Действие при запуске** задайте значение **Указанная страница** и выберите StringReverserService.xamlx в качестве стартовой страницы.  
  
6.  Откройте файл StringReverserService.xamlx в конструкторе и удалите существующие действия `ReceiveRequest` и `SendReply`, затем перетащите действие `ReceiveAndSendReply` в существующее действие последовательности.  
  
    1.  Параметру **OperationName** задайте значение ReverseString.  
  
    2.  Параметру **ServiceContractName** задайте значение IReverseString.  
  
    3.  Установите флажок **CanCreateInstance**.  
  
7.  Выберите действие **SequentialService**, после чего перейдите на вкладку **Переменные** внизу конструктора.Создайте две новые переменные типа String с именами StringToReverse и ReversedStringToReturn.  
  
8.  В действии **Receive** перейдите по ссылке **Define**.Выберите **Параметры** и создайте параметр типа String с именем InputString, назначенный StringToReverse.  
  
9. В действии **SendReplyToReceive** перейдите по ссылке **Define**.Выберите **Параметры** и создайте параметр типа String с именем ReversedString, назначенный ReversedStringToReturn.  
  
10. Чтобы реализовать логику для службы, создайте в проекте новый класс с именем StringLibrary.Замените определение класса на следующий код.  
  
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
  
11. Чтобы вызвать метод ReverseString при вводе, перетащите действие **InvokeMethod** из области элементов в пространство между действиями **Receive** и **SendReply**.Установите свойства действия следующим образом.  
  
    1.  **MethodName**: ReverseString  
  
    2.  **Result**: ReversedStringToReturn  
  
    3.  **Параметры**: создайте новый параметр, где **Direction** имеет значение In, **Type** ― String и **Value** ― StringToReverse.  
  
    4.  **TargetType**: NestedServices.StringLibrary  
  
12. Проверьте службу, нажав клавишу F5.В открывшемся клиенте теста WCF дважды щелкните метод ReverseString\(\).В качестве значения параметра InputString в области запросов введите `Sample`.Нажмите кнопку **Вызвать**.Служба должна вернуть «elpmaS».  
  
### Создание службы рабочего процесса UpperCaser  
  
1.  Щелкните проект NestedServices правой кнопкой мыши и выберите пункт **Добавить**, **Новый элемент**.В узле **Рабочий процесс** выберите **Служба рабочего процесса WCF** и присвойте новой службе имя `UpperCaserService`.Нажмите кнопку **Добавить**.После этого в проект должна будет быть добавлена новая служба рабочего процесса с именем UpperCaserService.xamlx.  
  
2.  Откройте файл UpperCaserService.xamlx в конструкторе и удалите существующие действия **ReceiveRequest** и `SendReply`, после чего перетащите действие `ReceiveAndSendReply` в существующее действие последовательности.  
  
    1.  Параметру **OperationName** задайте значение UpperCaseString.  
  
    2.  Параметру **ServiceContractName** задайте значение IUpperCaseString.  
  
    3.  Установите флажок **CanCreateInstance**.  
  
3.  Выберите действие SequentialService, затем перейдите на вкладку **Переменные** в нижней части конструктора.Создайте три новые переменные типа String с именами StringToUpper, StringToReverse и StringToReturn.  
  
4.  В действии **Receive** перейдите по ссылке **Define**.Выберите **Параметры** и создайте параметр типа String с именем InputString, назначенный StringToUpper.  
  
5.  В действии **SendReplyToReceive** перейдите по ссылке **Define**.Выберите **Параметры** и создайте параметр типа String с именем ModifiedString, назначенный StringToReturn.  
  
6.  Чтобы реализовать логику для службы, создайте в проекте с помощью следующего кода новый метод в классе StringLibrary.  
  
    ```  
    public static String UpperCaseString(string StringToUpperCase)  
    {  
         return StringToUpperCase.ToUpper();  
  
    }  
  
    ```  
  
7.  Чтобы вызвать метод UpperCaseString при вводе, перетащите действие **InvokeMethod** из области элементов в пространство между действиями **Receive** и **SendReply**.Установите свойства действия следующим образом.  
  
    1.  **MethodName**: UpperCaseString  
  
    2.  **Result**: StringToReverse  
  
    3.  **Параметры**: создайте новый параметр, где **Direction** имеет значение In, **Type** ― String и **Value** ― StringToUpper.  
  
    4.  **TargetType**: NestedServices.StringLibrary  
  
8.  Теперь для измененной строки мы вызовем первую службу.Щелкните правой кнопкой мыши проект и выберите команду **Добавить ссылку на службу**.Добавьте ссылку на службу по адресу http:\/\/localhost\/NestedServices\/StringReverserService.xamlx и постройте проект для создания настраиваемого действия для доступа к первой веб\-службе.  
  
9. Перетащите экземпляр нового действия на рабочий процесс, в область между действием **InvokeMethod** и действиями **SendReplyToReceive**.Назначьте переменную StringToReverse свойству InputString нового действия, а переменную StringToReturn ― свойству StringToReturn.  
  
10. Откройте страницу «Свойства» для проекта NestedServices и задайте параметру **Указанная страница** на вкладке **Веб** значение UpperCaserService.xamlx.  
  
11. Проверьте службу, нажав клавишу F5.В открывшемся клиенте теста WCF дважды щелкните метод ReverseString\(\).В качестве значения параметра InputString в области запросов введите `Sample`.Нажмите кнопку **Вызвать**.Служба должна вернуть «ELPMAS».  
  
### Создание клиента для вызова служб  
  
1.  Добавьте в решение новый проект консольного приложения с именем Client.  
  
2.  Щелкните правой кнопкой мыши проект клиента и выберите команду **Добавить ссылку на службу**.В открывшемся окне нажмите **Найти**.Выберите StringReverserService.xamlx и в качестве пространства имен введите ReverseService.Нажмите кнопку **ОК**.  
  
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