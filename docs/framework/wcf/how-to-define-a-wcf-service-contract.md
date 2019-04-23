---
title: Учебник. Определение контракта службы Windows Communication Foundation
ms.date: 03/19/2019
helpviewer_keywords:
- service contracts [WCF], defining
dev_langs:
- CSharp
- VB
ms.assetid: 67bf05b7-1d08-4911-83b7-a45d0b036fc3
ms.openlocfilehash: a1908339460191fcb81d03d45c56dd57b2cf4c4e
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59228397"
---
# <a name="tutorial-define-a-windows-communication-foundation-service-contract"></a>Учебник. Определение контракта службы Windows Communication Foundation

В данном учебнике первый из пяти шагов, необходимых для создания базового приложения Windows Communication Foundation (WCF). Обзор руководства, см. в разделе [руководства: Начало работы с приложениями Windows Communication Foundation](getting-started-tutorial.md).

При создании службы WCF, в первую очередь является определение контракта службы. В контракте службы указаны операции, поддерживаемые службой. Операцию можно представлять себе как метод веб-службы. Вы создаете контракты служб, определяя визуального C# или Visual Basic (Visual Basic) интерфейса. Интерфейс имеет следующие характеристики:

- Каждый метод в интерфейсе соответствует определенной операции службы. 
- Для каждого интерфейса, необходимо применить <xref:System.ServiceModel.ServiceContractAttribute> атрибута.
- Для каждой операции или метода, необходимо применить <xref:System.ServiceModel.OperationContractAttribute> атрибута. 

В этом руководстве вы узнаете, как:
> [!div class="checklist"]
> - Создание **библиотека службы WCF** проекта.
> - Определите интерфейс контракта службы.

## <a name="create-a-wcf-service-library-project-and-define-a-service-contract-interface"></a>Создайте проект библиотеки служб WCF и определить интерфейс контракта службы

1. Откройте Visual Studio от имени администратора. Чтобы сделать это, выберите в программе Visual Studio в **запустить** меню, а затем выберите **дополнительные** > **Запуск от имени администратора** в контекстном меню.

2. Создание **библиотека службы WCF** проекта.

   1. В меню **Файл** выберите пункт **Создать** > **Проект**.

   2. В **новый проект** диалоговое окно, в левой части окна разверните **Visual C#** или **Visual Basic**, а затем выберите **WCF** категории. Visual Studio отображает список шаблонов проектов в центральной части окна. Выберите **библиотека службы WCF**.

      > [!NOTE]
      > Если вы не видите **WCF** Категория шаблона проекта, может потребоваться установить **Windows Communication Foundation** компонент Visual Studio. В **новый проект** выберите **открыть установщик Visual Studio** ссылку в левой части. Выберите **отдельные компоненты** вкладке, а затем найдите и выберите **Windows Communication Foundation** под **действия разработки** категории. Выберите **изменить** для начала установки компонента.

   3. В нижней части окна, введите *GettingStartedLib* для **имя** и *GettingStarted* для **имя решения**. 

   4. Нажмите кнопку **ОК**.

      Visual Studio создает проект, который имеет три файла: *IService1.cs* (или *IService1.vb* для проекта Visual Basic), *Service1.cs* (или *Service1.vb* для проекта Visual Basic), и  *App.config*. Visual Studio определяет эти файлы следующим образом: 
      - *IService1* файл содержит определение контракта службы по умолчанию. 
      - *Service1* файл содержит реализацию по умолчанию контракта службы. 
      - *App.config* файл содержит сведения о конфигурации, необходимые для загрузки службы по умолчанию с помощью средства узел службы WCF Visual Studio. Дополнительные сведения о средстве WCF Service Host см. в разделе [узел службы WCF (WcfSvcHost.exe)](wcf-service-host-wcfsvchost-exe.md).

      > [!NOTE]
      > Если вы установили Visual Studio с параметрами среды разработки Visual Basic, решение может быть скрыт. Если это так, выберите **параметры** из **средства** меню, затем выберите **проекты и решения** > **Общие** в **параметры** окна. Выберите **всегда показывать решение**. Кроме того, убедитесь, что **сохранять новые проекты при создании** выбран.

3. Из **обозревателе решений**откройте **IService1.cs** или **IService1.vb** файл и замените его код следующим кодом:

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

     В этом контракте определен калькулятор в сети. Обратите внимание, что `ICalculator` интерфейс отмечен атрибутом <xref:System.ServiceModel.ServiceContractAttribute> атрибут (упрощенная как `ServiceContract`). Этот атрибут определяет пространство имен для устранения неоднозначности имени контракта. Каждая операция калькулятора с помечает код <xref:System.ServiceModel.OperationContractAttribute> атрибут (упрощенная как `OperationContract`).

## <a name="next-steps"></a>Следующие шаги

В этом руководстве вы узнали, как:
> [!div class="checklist"]
> - Создайте проект библиотеки служб WCF.
> - Определите интерфейс контракта службы.

Перейдите к следующему руководству, чтобы узнать, как реализовать контракт службы WCF.

> [!div class="nextstepaction"]
> [Учебник. Реализация контракта службы WCF](how-to-implement-a-wcf-contract.md)
