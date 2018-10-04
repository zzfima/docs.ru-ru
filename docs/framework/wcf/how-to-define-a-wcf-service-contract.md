---
title: Практическое руководство. Определение контракта службы Windows Communication Foundation
ms.date: 09/14/2018
helpviewer_keywords:
- service contracts [WCF], defining
dev_langs:
- CSharp
- VB
ms.assetid: 67bf05b7-1d08-4911-83b7-a45d0b036fc3
ms.openlocfilehash: 9f7f696b1f5be2e96c50938f4627271d891deb32
ms.sourcegitcommit: 69229651598b427c550223d3c58aba82e47b3f82
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/04/2018
ms.locfileid: "48582204"
---
# <a name="how-to-define-a-windows-communication-foundation-service-contract"></a>Практическое руководство. Определение контракта службы Windows Communication Foundation
Это первый из шести задач, необходимых для создания базового приложения Windows Communication Foundation (WCF). Общие сведения обо всех шести задачах можно получить в разделе [Учебник по началу работы](../../../docs/framework/wcf/getting-started-tutorial.md).

 При создании службы WCF, первым делом следует определить контракт службы. В контракте службы указаны операции, поддерживаемые службой. Операцию можно представлять себе как метод веб-службы. Контракты создаются путем определения интерфейса C++, C# или Visual Basic. Каждый метод в интерфейсе соответствует определенной операции службы. К каждому интерфейсу должен быть применен атрибут <xref:System.ServiceModel.ServiceContractAttribute>, и к каждой операции должен быть применен атрибут <xref:System.ServiceModel.OperationContractAttribute>. Если один из методов в интерфейсе, имеющем атрибут <xref:System.ServiceModel.ServiceContractAttribute>, не имеет атрибута <xref:System.ServiceModel.OperationContractAttribute>, этот метод не представлен службой.

 Код, используемый для выполнения этой задачи, приведен в примере после описания процедуры.

## <a name="define-a-service-contract"></a>Определите контракт службы

1. Откройте Visual Studio с правами администратора, щелкнув правой кнопкой мыши в программе в **запустить** меню и выбрав **дополнительные** > **Запуск от имени администратора**.

2. Создайте проект библиотеки служб WCF.

   1. В меню **Файл** выберите пункт **Создать** > **Проект**.

   2. В **новый проект** диалоговое окно, в левой части окна разверните **Visual C#** или **Visual Basic**, а затем выберите **WCF** категории. Шаблоны проектов отображаются в центральной части диалогового окна. Выберите **библиотека службы WCF**.

   3. Введите `GettingStartedLib` в **имя** textbox и `GettingStarted` в **имя решения** текстовое поле в нижней части диалогового окна.

   > [!NOTE]
   > Если вы не видите **WCF** Категория шаблона проекта, может потребоваться установить **Windows Communication Foundation** компонент Visual Studio. В **новый проект** диалогового окна выберите ссылку **открыть установщик Visual Studio**. Выберите **отдельные компоненты** вкладке, а затем найдите и выберите **Windows Communication Foundation** под **действия разработки** категории. Выберите **изменить** для начала установки компонента.

   Visual Studio создает проект, содержащий 3 файла: IService1.cs (или IService1.vb), Service1.cs (или Service1.vb) и App.config. В файле IService1 содержится контракт службы по умолчанию. В файле Service1 содержится контракт службы, реализованный методом по умолчанию. В файле App.config содержатся настройки, необходимые для загрузки службы по умолчанию средством WCF Service Host в Visual Studio. Дополнительные сведения о средстве WCF Service Host см. в разделе [узел службы WCF (WcfSvcHost.exe)](../../../docs/framework/wcf/wcf-service-host-wcfsvchost-exe.md)

3. Откройте файл IService1.cs или IService1.vb и удалите код в объявление пространства имен, оставив объявление пространства имен. В пределах объявления пространства имен определите новый интерфейс с именем `ICalculator`, как показано в приведенном ниже примере кода.

    ```csharp
    using System;
    using System.ServiceModel;

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

    ```vb
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

     В этом контракте определен калькулятор в сети. Обратите внимание, что интерфейс `ICalculator` помечен атрибутом <xref:System.ServiceModel.ServiceContractAttribute>. Этот атрибут определяет пространство имен, которое используется для устранения неоднозначности имени контракта. Каждая операция калькулятора помечена атрибутом <xref:System.ServiceModel.OperationContractAttribute>.

## <a name="next-steps"></a>Следующие шаги

> [!div class="nextstepaction"]
> [Практическое: реализация контракта службы](../../../docs/framework/wcf/how-to-implement-a-wcf-contract.md)

## <a name="see-also"></a>См. также

- <xref:System.ServiceModel.ServiceContractAttribute>
- <xref:System.ServiceModel.OperationContractAttribute>
- [Практическое руководство. Реализация контракта службы](../../../docs/framework/wcf/how-to-implement-a-wcf-contract.md)
- [Начало работы](../../../docs/framework/wcf/samples/getting-started-sample.md)
- [Резидентное размещение](../../../docs/framework/wcf/samples/self-host.md)