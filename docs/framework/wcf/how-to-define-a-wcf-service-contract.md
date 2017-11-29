---
title: "Практическое руководство. Определение контракта службы Windows Communication Foundation"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: service contracts [WCF], defining
ms.assetid: 67bf05b7-1d08-4911-83b7-a45d0b036fc3
caps.latest.revision: "58"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 2ffe53d3e44f86feadc292eccb1692bd58a0c056
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-define-a-windows-communication-foundation-service-contract"></a>Практическое руководство. Определение контракта службы Windows Communication Foundation
Это первый из шести шагов, необходимых для создания базового приложения [!INCLUDE[indigo1](../../../includes/indigo1-md.md)]. Общие сведения обо всех шести задач см. в разделе [учебник по началу работы](../../../docs/framework/wcf/getting-started-tutorial.md) раздела.  
  
 При создании службы [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] необходимо в первую очередь определить контракт службы. В контракте службы указаны операции, поддерживаемые службой. Операцию можно представлять себе как метод веб-службы. Контракты создаются путем определения интерфейса C++, C# или Visual Basic. Каждый метод в интерфейсе соответствует определенной операции службы. К каждому интерфейсу должен быть применен атрибут <xref:System.ServiceModel.ServiceContractAttribute>, и к каждой операции должен быть применен атрибут <xref:System.ServiceModel.OperationContractAttribute>. Если один из методов в интерфейсе, имеющем атрибут <xref:System.ServiceModel.ServiceContractAttribute>, не имеет атрибута <xref:System.ServiceModel.OperationContractAttribute>, этот метод не представлен службой.  
  
 Код, используемый для выполнения этой задачи, приведен в примере после описания процедуры.  
  
### <a name="to-define-a-service-contract"></a>Определение контракта службы  
  
1.  Откройте [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)] от имени администратора, щелкнув правой кнопкой мыши программу в **запустить** , выберите в меню **Запуск от имени администратора**.  
  
2.  Создание проекта библиотеки службы WCF, щелкнув **файл** , выберите в меню **New**, **проекта**. В **новый проект** диалоговое окно, в левой части диалогового окна разверните **Visual C#** для проекта C# или **другие языки** и затем **Visual Basic** для проекта Visual Basic. В выбранном языке выберите **WCF** список шаблонов проекта отображается в центральной части диалогового окна. Выберите **библиотеки службы WCF**и тип `GettingStartedLib` в **имя** текстового поля и `GettingStarted` в **имя решения** текстовое поле в нижней части диалогового окна.  
  
3.  Visual Studio создаст проект, содержащий 3 файла: IService1.cs (или IService1.vb), Service1.cs (или Service1.vb) и App.config.  В файле IService1 содержится контракт службы по умолчанию.  В файле Service1 содержится контракт службы, реализованный методом по умолчанию. В файле App.config содержатся настройки, необходимые для загрузки службы по умолчанию средством WCF Service Host в Visual Studio. Дополнительные сведения о средстве узел службы WCF см. в разделе [узел службы WCF (WcfSvcHost.exe)](../../../docs/framework/wcf/wcf-service-host-wcfsvchost-exe.md)  
  
4.  Откройте файл IService1.cs или IService1.vb и удалите код в пределах объявления пространства имен, оставив при этом само объявление пространства имен. В пределах объявления пространства имен определите новый интерфейс с именем `ICalculator`, как показано в приведенном ниже примере кода.  
  
    ```  
    // IService.cs  
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
  
     В этом контракте определен калькулятор в сети. Обратите внимание, что интерфейс `ICalculator` помечен атрибутом <xref:System.ServiceModel.ServiceContractAttribute>. Этот атрибут определяет пространство имен, которое используется для устранения неоднозначности имени контракта. Каждая операция калькулятора помечена атрибутом <xref:System.ServiceModel.OperationContractAttribute>.  
  
    > [!NOTE]
    >  При использовании атрибутов для аннотирования интерфейса, члена или класса в имени атрибута можно опускать часть Attribute. Таким образом, <xref:System.ServiceModel.ServiceContractAttribute> изменится на `[ServiceContract]` в C# или на `<ServiceContract>` в Visual Basic.  
  
## <a name="see-also"></a>См. также  
 <xref:System.ServiceModel.ServiceContractAttribute>  
 <xref:System.ServiceModel.OperationContractAttribute>  
 [Практическое руководство. Реализация контракта службы](../../../docs/framework/wcf/how-to-implement-a-wcf-contract.md)  
 [Начало работы](../../../docs/framework/wcf/samples/getting-started-sample.md)  
 [Резидентное размещение](../../../docs/framework/wcf/samples/self-host.md)
