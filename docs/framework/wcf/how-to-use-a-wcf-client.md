---
title: Практическое руководство. Использование клиента Windows Communication Foundation
ms.date: 03/30/2017
helpviewer_keywords:
- WCF clients [WCF], using
ms.assetid: 190349fc-0573-49c7-bb85-8e316df7f31f
ms.openlocfilehash: 79431588e27b02a40d5898929f1bdf644c8a79cd
ms.sourcegitcommit: 15109844229ade1c6449f48f3834db1b26907824
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2018
---
# <a name="how-to-use-a-windows-communication-foundation-client"></a>Практическое руководство. Использование клиента Windows Communication Foundation
Это последний из шести шагов, необходимых для создания базового приложения Windows Communication Foundation (WCF). Общие сведения обо всех шести задач см. в разделе [учебник по началу работы](../../../docs/framework/wcf/getting-started-tutorial.md) раздела.  
  
 После создания и настройки прокси службы Windows Communication Foundation (WCF) можно создать экземпляр клиента и клиентское приложение можно скомпилировать и использовать для взаимодействия со службой WCF. В этом разделе описаны процедуры создания и использования клиента WCF. Эта процедура выполняет три операции.  
  
1.  Создает экземпляр класса клиента WCF.  
  
2.  Вызывает операции службы из созданной учетной записи-посредника.  
  
3.  Закрывает клиент после завершения вызова операции.  
  
### <a name="to-use-a-windows-communication-foundation-client"></a>Использование клиента Windows Communication Foundation  
  
1.  Откройте файл Program.cs или Program.vb из проекта GettingStartedClient и замените существующий код в файлах следующим:  
  
    ```  
    using System;  
    using System.Collections.Generic;  
    using System.Linq;  
    using System.Text;  
    using GettingStartedClient.ServiceReference1;  
  
    namespace GettingStartedClient  
    {  
        class Program  
        {  
            static void Main(string[] args)  
            {  
                //Step 1: Create an instance of the WCF proxy.  
                CalculatorClient client = new CalculatorClient();  
  
                // Step 2: Call the service operations.  
                // Call the Add service operation.  
                double value1 = 100.00D;  
                double value2 = 15.99D;  
                double result = client.Add(value1, value2);  
                Console.WriteLine("Add({0},{1}) = {2}", value1, value2, result);  
  
                // Call the Subtract service operation.  
                value1 = 145.00D;  
                value2 = 76.54D;  
                result = client.Subtract(value1, value2);  
                Console.WriteLine("Subtract({0},{1}) = {2}", value1, value2, result);  
  
                // Call the Multiply service operation.  
                value1 = 9.00D;  
                value2 = 81.25D;  
                result = client.Multiply(value1, value2);  
                Console.WriteLine("Multiply({0},{1}) = {2}", value1, value2, result);  
  
                // Call the Divide service operation.  
                value1 = 22.00D;  
                value2 = 7.00D;  
                result = client.Divide(value1, value2);  
                Console.WriteLine("Divide({0},{1}) = {2}", value1, value2, result);  
  
                //Step 3: Closing the client gracefully closes the connection and cleans up resources.  
                client.Close();  
            }  
        }  
    }  
    ```  
  
    ```  
    Imports System  
    Imports System.Collections.Generic  
    Imports System.Text  
    Imports System.ServiceModel  
    Imports GettingStartedClientVB2.ServiceReference1  
  
    Module Module1  
  
        Sub Main()  
            ' Step 1: Create an instance of the WCF proxy  
            Dim Client As New CalculatorClient()  
  
            'Step 2: Call the service operations.  
            'Call the Add service operation.  
            Dim value1 As Double = 100D  
            Dim value2 As Double = 15.99D  
            Dim result As Double = Client.Add(value1, value2)  
            Console.WriteLine("Add({0},{1}) = {2}", value1, value2, result)  
  
            'Call the Subtract service operation.  
            value1 = 145D  
            value2 = 76.54D  
            result = Client.Subtract(value1, value2)  
            Console.WriteLine("Subtract({0},{1}) = {2}", value1, value2, result)  
  
            'Call the Multiply service operation.  
            value1 = 9D  
            value2 = 81.25D  
            result = Client.Multiply(value1, value2)  
            Console.WriteLine("Multiply({0},{1}) = {2}", value1, value2, result)  
  
            'Call the Divide service operation.  
            value1 = 22D  
            value2 = 7D  
            result = Client.Divide(value1, value2)  
            Console.WriteLine("Divide({0},{1}) = {2}", value1, value2, result)  
  
            ' Step 3: Closing the client gracefully closes the connection and cleans up resources.  
            Client.Close()  
  
            Console.WriteLine()  
            Console.WriteLine("Press <ENTER> to terminate client.")  
            Console.ReadLine()  
  
        End Sub  
  
    End Module  
    ```  
  
     Обратите внимание на инструкции using и imports для импорта GettingStartedClient.ServiceReference1. Эта инструкция импортирует код, созданный функцией «Добавить ссылки на службу» средства Visual Studio. Код создает WCF-прокси и затем вызывает каждую операцию службы, предоставленную службой калькулятора, закрывает прокси и завершает работу.  
  
 Вы завершили работу с учебником. Был определен и реализован контракт службы, создан WCF-прокси, настроено клиентское приложение WCF, и использованы прокси для вызова операций службы. Чтобы проверить приложение, сначала запустите GettingStartedHost для запуска службы, а затем сам клиент GettingStartedClient. Вывод из GettingStartedHost должен выглядеть следующим образом:  
  
```Output  
The service is ready.Press <ENTER> to terminate service.Received Add(100,15.99)Return: 115.99Received Subtract(145,76.54)Return: 68.46Received Multiply(9,81.25)Return: 731.25Received Divide(22,7)Return: 3.14285714285714  
```  
  
 Вывод GettingStartedClient должен выглядеть следующим образом:  
  
```Output  
Add(100,15.99) = 115.99Subtract(145,76.54) = 68.46Multiply(9,81.25) = 731.25Divide(22,7) = 3.14285714285714Press <ENTER> to terminate client.  
```  
  
## <a name="see-also"></a>См. также  
 [Создание клиентов](../../../docs/framework/wcf/building-clients.md)  
 [Практическое руководство. Создание клиента](../../../docs/framework/wcf/how-to-create-a-wcf-client.md)  
 [Руководство по началу работы](../../../docs/framework/wcf/getting-started-tutorial.md)  
 [Базовое программирование для WCF](../../../docs/framework/wcf/basic-wcf-programming.md)  
 [Практическое руководство. Создание дуплексного контракта](../../../docs/framework/wcf/feature-details/how-to-create-a-duplex-contract.md)  
 [Практическое руководство. Доступ к службам с дуплексным контрактом](../../../docs/framework/wcf/feature-details/how-to-access-services-with-a-duplex-contract.md)  
 [Начало работы](../../../docs/framework/wcf/samples/getting-started-sample.md)  
 [Резидентное размещение](../../../docs/framework/wcf/samples/self-host.md)
