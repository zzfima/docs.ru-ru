---
title: "Обработка заказов с помощью политики"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 66833724-dc36-4fad-86b0-59ffeaa3ba6a
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 4aaab8fca4693f6b253d48f066e644cc76637241
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="order-processing-with-policy"></a>Обработка заказов с помощью политики
В данном образце политики обработки заказов продемонстрированы некоторые ключевые функции, представленные в [!INCLUDE[netfx35_long](../../../../includes/netfx35-long-md.md)] платформы Windows Workflow Foundation (WF). В обработчике правил WF реализованы следующие новые функции:  
  
-   поддержка перегрузки операторов;  
  
-   поддержка оператора `new`, который позволяет пользователям создавать новые объекты и массивы из правил WF;  
  
-   поддержка методов расширения, которые обеспечивают совместимость пользовательских вызовов методов расширения из WF со стилями программирования С#.  
  
> [!NOTE]
>  Для этого образца необходимо установить, выполнить сборку и запустить [!INCLUDE[netfx35_long](../../../../includes/netfx35-long-md.md)]. [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] необходимо, чтобы открыть файлы проекта и решения.  
  
 В данном образце демонстрируется проект `OrderProcessingPolicy`, в котором вводится заказ клиента, состоящий из нумерованного списка доступных элементов и почтового индекса. Обработка заказа выполняется успешно, если обе записи верны, в противном случае политика создает объекты ошибок, используя перегруженный оператор `+` и предварительно определенный метод расширения, чтобы информировать пользователей об ошибках.  
  
> [!NOTE]
>  [!INCLUDE[crabout](../../../../includes/crabout-md.md)]методах расширения см. в разделе [спецификация C# версии 3.0](http://go.microsoft.com/fwlink/?LinkId=95402).  
  
 Образец включает следующие проекты:  
  
-   `OrderErrorLibrary`  
  
     `OrderErrorLibrary` - библиотека классов, которая определяет классы `OrderError` и `OrderErrorCollection`. При неверном вводе создается экземпляр `OrderError`. Библиотека также предоставляет методы расширения для класса `OrderErrorCollection`, который выдает свойство `ErrorText` для всех объектов `OrderError` в коллекции `OrderErrorCollection`.  
  
-   `OrderProcessingPolicy`  
  
     Проект `OrderProcessingPolicy` представляет собой консольное приложение WF, которое определяет одно действие `PolicyFromFile`. В данном действии содержатся следующие правила:  
  
    -   `invalidItemNum`  
  
         Данное правило проверяет, что элемент имеет номер от 1 до 6 включительно. Если номер элемента находится в пределах допустимого диапазона, правило ничего не делает (кроме печати в консоль). Если номер элемента находится вне диапазона 1-6, правило `invalidItemNum` выполняет перечисленные ниже действия.  
  
        1.  Создает новый объект `OrderError`, передавая ему заданный номер элемента, и устанавливает свойства `ErrorText` и `CustomerName` для объекта.  
  
        2.  Создает объект `invalidItemNumErrorCollection`.  
  
        3.  Добавляет новый экземпляр `OrderError` в коллекцию `invalidItemNumErrorCollection`.  
  
         Таким образом реализована функция поддержки оператора `new`, с помощью которого в правилах можно создавать экземпляры объектов.  
  
    -   `invalidZip`  
  
         Это правило проверяет, что почтовый индекс содержит 5 цифр и находится в диапазоне от 600 до 99998. Если почтовый индекс находится в пределах допустимого диапазона, правило ничего не делает (кроме печати в консоль). Если длина почтового индекса меньше 5 цифр или индекс находится вне диапазона 00600–99998, правило `invalidZip` выполняет перечисленные ниже действия.  
  
        1.  Создает объект `OrderError`, передавая ему заданный почтовый индекс, и устанавливает свойства `ErrorText` и `CustomerName` для объекта.  
  
        2.  Создает объект `invalidZipCodeErrorCollection`.  
  
        3.  Добавляет новый экземпляр `OrderError` в новую коллекцию `invalidZipCodeErrorCollection`.  
  
         Таким образом в данном правиле снова реализована функция поддержки оператора `new`, с помощью которого в правилах можно создавать экземпляры объектов.  
  
    -   `displayErrors`  
  
         Это правило проверяет наличие ошибок, добавленных предыдущими двумя правилами в два объекта `OrderErrorCollection`: `invalidItemNumErrorCollection` и `invalidIZipCodeErrorCollection`. При обнаружении ошибок (`invalidItemNumErrorCollection` или `invalidZipCodeErrorCollection` не равны `null`) правило выполняет перечисленные ниже действия.  
  
        1.  Вызывает перегруженный `+` оператор, чтобы скопировать содержимое `invalidItemNumErrorCollection` и `invalidZipCodeErrorCollection` для `invalidOrdersCollection``OrderErrorCollection` экземпляра.  
  
        2.  Вызывает метод расширения `PrintOrderErrors` для коллекции `invalidOrdersCollection` и выдает свойство `ErrorText` для всех объектов `orderError` в коллекции `invalidOrdersCollection`.  
  
 Перегруженный оператор `+` для объекта `OrderErrorCollection` определяется в классе `OrderErrorCollection` в проекте `OrderErrorLibrary`. Он объединяет два объекта `OrderErrorCollection` в один объект `OrderErrorCollection`.  
  
 Метод расширения `PrintOrderErrors` также определяется в проекте `OrderErrorLibrary`. Методы расширения являются новой функциональной возможностью С#, которая позволяет разработчикам добавлять новые методы в открытый контракт существующего CLR-типа без необходимости создавать класс, производный от данного типа, или повторно компилировать исходный тип.  
  
 При выполнении образца запрашивается ввод имени, номер приобретаемого товара и почтовый индекс. Эти данные затем проверяются правилами, определенными в данном действии политики. В следующем образце демонстрируется результат действия данной программы.  
  
```  
Please enter your name: John  
  
What would you like to purchase?  
        (1) Vista Ultimate DVD  
        (2) Vista Ultimate Upgrade DVD  
        (3) Vista Home Premium DVD  
        (4) Vista Home Premium Upgrade DVD  
        (5) Vista Home Basic DVD  
        (6) Vista Home Basic Upgrade DVD  
  
Please enter an item number: 1  
  
Please enter your 5-Digit zip code: 98102  
  
        Executing Rule: invalidItemNum  
        Executing Rule: invalidZip  
        Executing Rule: displayErrors  
  
                              Thank you for your order, it has been processed.  
  
Workflow Completed  
Another Order? (Y/N): y  
  
Please enter your name: Joel  
  
What would you like to purchase?  
        (1) Vista Ultimate DVD  
        (2) Vista Ultimate Upgrade DVD  
        (3) Vista Home Premium DVD  
        (4) Vista Home Premium Upgrade DVD  
        (5) Vista Home Basic DVD  
        (6) Vista Home Basic Upgrade DVD  
  
Please enter an item number: 8  
  
Please enter your 5-Digit zip code: 0000  
  
        Executing Rule: invalidItemNum  
        Executing Rule: invalidZip  
        Executing Rule: displayErrors  
  
                              Your order contains the following error(s)  
  
Error: No item number found. Please choose an available item.  
Error: Invalid zip code. Please choose a zip code between 00600 and 99998.  
  
Workflow Completed  
Another Order? (Y/N): n  
```  
  
### <a name="to-set-up-build-and-run-the-sample"></a>Настройка, сборка и выполнение образца  
  
1.  Откройте файл проекта "OrderProcessingPolicy.sln" в [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].  
  
2.  В данном решении находятся два различных проекта: `OrderErrorLibrary` и `OrderProcessingPolicy`. Проект `OrderProcessingPolicy` использует классы и методы, определенные в `OrderErrorLibrary`.  
  
3.  Выполните построение всех проектов.  
  
4.  Щелкните **Запуск**.  
  
> [!IMPORTANT]
>  Образцы уже могут быть установлены на компьютере. Перед продолжением проверьте следующий каталог (по умолчанию).  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Если этот каталог не существует, перейдите на страницу [Примеры Windows Communication Foundation (WCF) и Windows Workflow Foundation (WF) для .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) , чтобы скачать все примеры [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] . Этот образец находится в следующем каталоге:  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Rules\Policy\OrderProcessingPolicy`