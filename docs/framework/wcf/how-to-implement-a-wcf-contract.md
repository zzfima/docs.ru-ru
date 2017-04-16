---
title: "Практическое руководство. Реализация контракта службы Windows Communication Foundation | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
helpviewer_keywords: 
  - "контракты служб [WCF], реализация"
ms.assetid: d5ab51ba-61ae-403e-b3c8-e2669e326806
caps.latest.revision: 38
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 38
---
# Практическое руководство. Реализация контракта службы Windows Communication Foundation
Это вторая из шести задач, выполнение которых необходимо для создания базовой службы [!INCLUDE[indigo1](../../../includes/indigo1-md.md)] и клиента, который может вызывать службу.  Общие сведения обо всех шести задачах см. в разделе [Учебник по началу работы](../../../docs/framework/wcf/getting-started-tutorial.md).  
  
 Следующий шаг по созданию приложения WCF \- это реализация интерфейса службы.  Это предполагает создание класса с именем `CalculatorService`, реализующего пользовательский интерфейс `ICalculator`.  
  
### Реализация контракта службы WCF  
  
1.  Откройте файл Service1.cs или Service1.vb и добавьте следующий код:  
  
    ```csharp  
    //Service1.cs  
    using System;  
    using System.Collections.Generic;  
    using System.Linq;  
    using System.Runtime.Serialization;  
    using System.ServiceModel;  
    using System.Text;  
  
    namespace GettingStartedLib  
    {  
        public class CalculatorService : ICalculator  
        {  
            public double Add(double n1, double n2)  
            {  
                double result = n1 + n2;  
                Console.WriteLine("Received Add({0},{1})", n1, n2);  
                // Code added to write output to the console window.  
                Console.WriteLine("Return: {0}", result);  
                return result;  
            }  
  
            public double Subtract(double n1, double n2)  
            {  
                double result = n1 - n2;  
                Console.WriteLine("Received Subtract({0},{1})", n1, n2);  
                Console.WriteLine("Return: {0}", result);  
                return result;  
            }  
  
            public double Multiply(double n1, double n2)  
            {  
                double result = n1 * n2;  
                Console.WriteLine("Received Multiply({0},{1})", n1, n2);  
                Console.WriteLine("Return: {0}", result);  
                return result;  
            }  
  
            public double Divide(double n1, double n2)  
            {  
                double result = n1 / n2;  
                Console.WriteLine("Received Divide({0},{1})", n1, n2);  
                Console.WriteLine("Return: {0}", result);  
                return result;  
            }  
        }  
    }  
  
    ```  
  
    ```  
    ‘Service1.vb  
    Imports System  
    Imports System.ServiceModel  
  
    Namespace GettingStartedLib  
  
        Public Class CalculatorService  
            Implements ICalculator  
  
            Public Function Add(ByVal n1 As Double, ByVal n2 As Double) As Double Implements ICalculator.Add  
                Dim result As Double = n1 + n2  
                ' Code added to write output to the console window.  
                Console.WriteLine("Received Add({0},{1})", n1, n2)  
                Console.WriteLine("Return: {0}", result)  
                Return result  
            End Function  
  
            Public Function Subtract(ByVal n1 As Double, ByVal n2 As Double) As Double Implements ICalculator.Subtract  
                Dim result As Double = n1 - n2  
                Console.WriteLine("Received Subtract({0},{1})", n1, n2)  
                Console.WriteLine("Return: {0}", result)  
                Return result  
  
            End Function  
  
            Public Function Multiply(ByVal n1 As Double, ByVal n2 As Double) As Double Implements ICalculator.Multiply  
                Dim result As Double = n1 * n2  
                Console.WriteLine("Received Multiply({0},{1})", n1, n2)  
                Console.WriteLine("Return: {0}", result)  
                Return result  
  
            End Function  
  
            Public Function Divide(ByVal n1 As Double, ByVal n2 As Double) As Double Implements ICalculator.Divide  
                Dim result As Double = n1 / n2  
                Console.WriteLine("Received Divide({0},{1})", n1, n2)  
                Console.WriteLine("Return: {0}", result)  
                Return result  
  
            End Function  
        End Class  
    End Namespace  
    ```  
  
     Каждый метод реализует операцию калькулятора и выводит на консоль некоторый текст, чтобы упростить тестирование.  
  
## Пример  
 В следующем коде показан интерфейс, определяющий контракт, и реализация этого интерфейса.  
  
```  
// IService1.cs  
using System;  
using System.Collections.Generic;  
using System.Linq;  
using System.Runtime.Serialization;  
using System.ServiceModel;  
using System.Text;  
  
namespace GettingStartedLib  
{  
        [ServiceContract(Namespace = "http://Microsoft.ServiceModel.Samples")]  
        public interface ICalculator  
        {  
            [OperationContract]  
            double Add(double n1, double n2);  
            [OperationContract]  
            double Subtract(double n1, double n2);  
            [OperationContract]  
            double Multiply(double n1, double n2);  
            [OperationContract]  
            double Divide(double n1, double n2);  
        }  
}  
  
```  
  
```  
// Service1.cs  
using System;  
using System.Collections.Generic;  
using System.Linq;  
using System.Runtime.Serialization;  
using System.ServiceModel;  
using System.Text;  
  
namespace GettingStartedLib  
{  
    public class CalculatorService : ICalculator  
    {  
        public double Add(double n1, double n2)  
        {  
            double result = n1 + n2;  
            Console.WriteLine("Received Add({0},{1})", n1, n2);  
            // Code added to write output to the console window.  
            Console.WriteLine("Return: {0}", result);  
            return result;  
        }  
  
        public double Subtract(double n1, double n2)  
        {  
            double result = n1 - n2;  
            Console.WriteLine("Received Subtract({0},{1})", n1, n2);  
            Console.WriteLine("Return: {0}", result);  
            return result;  
        }  
  
        public double Multiply(double n1, double n2)  
        {  
            double result = n1 * n2;  
            Console.WriteLine("Received Multiply({0},{1})", n1, n2);  
            Console.WriteLine("Return: {0}", result);  
            return result;  
        }  
  
        public double Divide(double n1, double n2)  
        {  
            double result = n1 / n2;  
            Console.WriteLine("Received Divide({0},{1})", n1, n2);  
            Console.WriteLine("Return: {0}", result);  
            return result;  
        }  
    }  
}  
  
```  
  
```  
‘IService.vb  
Imports System  
Imports System.ServiceModel  
  
Namespace GettingStartedLib  
  
    <ServiceContract(Namespace:="http://Microsoft.ServiceModel.Samples")> _  
    Public Interface ICalculator  
  
        <OperationContract()> _  
        Function Add(ByVal n1 As Double, ByVal n2 As Double) As Double  
        <OperationContract()> _  
        Function Subtract(ByVal n1 As Double, ByVal n2 As Double) As Double  
        <OperationContract()> _  
        Function Multiply(ByVal n1 As Double, ByVal n2 As Double) As Double  
        <OperationContract()> _  
        Function Divide(ByVal n1 As Double, ByVal n2 As Double) As Double  
    End Interface  
End Namespace  
```  
  
```  
Imports System  
Imports System.ServiceModel  
  
Namespace GettingStartedLib  
  
    Public Class CalculatorService  
        Implements ICalculator  
  
        Public Function Add(ByVal n1 As Double, ByVal n2 As Double) As Double Implements ICalculator.Add  
            Dim result As Double = n1 + n2  
            ' Code added to write output to the console window.  
            Console.WriteLine("Received Add({0},{1})", n1, n2)  
            Console.WriteLine("Return: {0}", result)  
            Return result  
        End Function  
  
        Public Function Subtract(ByVal n1 As Double, ByVal n2 As Double) As Double Implements ICalculator.Subtract  
            Dim result As Double = n1 - n2  
            Console.WriteLine("Received Subtract({0},{1})", n1, n2)  
            Console.WriteLine("Return: {0}", result)  
            Return result  
  
        End Function  
  
        Public Function Multiply(ByVal n1 As Double, ByVal n2 As Double) As Double Implements ICalculator.Multiply  
            Dim result As Double = n1 * n2  
            Console.WriteLine("Received Multiply({0},{1})", n1, n2)  
            Console.WriteLine("Return: {0}", result)  
            Return result  
  
        End Function  
  
        Public Function Divide(ByVal n1 As Double, ByVal n2 As Double) As Double Implements ICalculator.Divide  
            Dim result As Double = n1 / n2  
            Console.WriteLine("Received Divide({0},{1})", n1, n2)  
            Console.WriteLine("Return: {0}", result)  
            Return result  
  
        End Function  
    End Class  
End Namespace  
```  
  
 Теперь контракт службы был создан и реализован.  Создайте решение, чтобы убедиться в отсутствии ошибок компиляции, затем переходите к разделу [Как размещать и запускать базовую службу](../../../docs/framework/wcf/how-to-host-and-run-a-basic-wcf-service.md) для запуска службы.  Сведения по устранению неполадок см. в разделе [Устранение неполадок, связанных с учебником по началу работы](../../../docs/framework/wcf/troubleshooting-the-getting-started-tutorial.md).  
  
## Компиляция кода  
 Если используется Visual Studio, выберите в меню Построение пункт Построить решение \(или нажмите сочетание клавиш CTRL\+SHIFT\+B\).  
  
## См. также  
 [Начало работы](../../../docs/framework/wcf/samples/getting-started-sample.md)   
 [Резидентное размещение](../../../docs/framework/wcf/samples/self-host.md)