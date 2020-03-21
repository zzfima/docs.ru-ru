---
title: 'Учебник: Определите контракт на обслуживание Фонда связи Windows'
ms.date: 03/19/2019
helpviewer_keywords:
- service contracts [WCF], defining
dev_langs:
- CSharp
- VB
ms.assetid: 67bf05b7-1d08-4911-83b7-a45d0b036fc3
ms.openlocfilehash: 7c1c42c4f22a1a9627c147440e8e198551470b7b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79184097"
---
# <a name="tutorial-define-a-windows-communication-foundation-service-contract"></a>Учебник: Определите контракт на обслуживание Фонда связи Windows

В этом уроке описана первая из пяти задач, необходимых для создания базового приложения Windows Communication Foundation (WCF). Для обзора учебников [см.](getting-started-tutorial.md)

При создании службы WCF ваша первая задача состоит в определении договора на обслуживание. Контракт службы определяет, какие операции поддерживает служба. Операцию можно представлять себе как метод веб-службы. Вы создаете сервисные контракты, определяя интерфейс СЗ или Visual Basic. Интерфейс имеет следующие характеристики:

- Каждый метод в интерфейсе соответствует определенной операции службы.
- Для каждого интерфейса необходимо <xref:System.ServiceModel.ServiceContractAttribute> применить атрибут.
- Для каждой операции/метода <xref:System.ServiceModel.OperationContractAttribute> необходимо применить атрибут.

В этом руководстве описано следующее:
> [!div class="checklist"]
>
> - Создайте проект **библиотеки обслуживания WCF.**
> - Определите интерфейс контракта на обслуживание.

## <a name="create-a-wcf-service-library-project-and-define-a-service-contract-interface"></a>Создание проекта Библиотеки обслуживания WCF и определение интерфейса контракта на обслуживание

1. Откройте Visual Studio от имени администратора. Для этого выберите программу Visual Studio в меню **«Пуск»,** а затем выберите **More** > Run в**качестве администратора** из меню ярлыка.

2. Создайте проект **библиотеки обслуживания WCF.**

   1. В меню **Файл** выберите пункт **Создать** > **Проект**.

   2. В диалоге **Нового проекта,** на левой стороне, расширьте **Visual C или** Visual **Basic,** а затем выберите категорию **WCF.** Visual Studio отображает список шаблонов проекта в центральной части окна. Выберите **библиотеку обслуживания WCF**.

      > [!NOTE]
      > Если вы не видите категорию шаблона проекта **WCF,** возможно, потребуется установить компонент **Windows Communication Foundation** visual Studio. В диалоговом окне **нового проекта** выберите ссылку Open Visual **Studio Installer** на левой стороне. Выберите вкладку **Отдельные компоненты,** а затем найдите и выберите **Фонд связи Windows** в категории **«Деятельность развития».** Выберите **изменение,** чтобы начать установку компонента.

   3. В нижней части окна введите *GettingStartedLib* для **имени** и *GettingStarted* для **имени решения.**

   4. Нажмите кнопку **ОК**.

      Visual Studio создает проект, который состоит из трех файлов: *IService1.cs* (или *IService1.vb* для визуального базового проекта), *Service1.cs* (или *Service1.vb* для визуального базового проекта) и *App.config*. Visual Studio определяет эти файлы следующим образом:
      - Файл *IService1* содержит определение контракта службы по умолчанию.
      - Файл *Service1* содержит выполнение контракта службы по умолчанию.
      - Файл *App.config* содержит информацию о конфигурации, необходимую для загрузки службы по умолчанию с помощью инструмента Visual Studio WCF Service Host. Для получения дополнительной информации об инструменте WCF Service Host [см.](wcf-service-host-wcfsvchost-exe.md)

      > [!NOTE]
      > Если вы установили Visual Studio с настройками среды Visual Basic, решение может быть скрыто. Если это так, выберите **Параметры** из меню **Инструментов,** а затем выберите **проекты и** > **общие** решения в окне **опционов.** Выберите **Всегда показывать решение.** Кроме того, убедитесь, что **Сохранение новых проектов при создании** выбрано.

3. От **Solution Explorer**откройте файл **IService1.cs** или **IService1.vb** и замените его код следующим кодом:

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

     В этом контракте определен калькулятор в сети. Обратите `ICalculator` внимание, что <xref:System.ServiceModel.ServiceContractAttribute> интерфейс помечен `ServiceContract`атрибутом (упрощенкак). Этот атрибут определяет пространство имен для того, чтобы отослать название контракта. Код помечает каждую <xref:System.ServiceModel.OperationContractAttribute> операцию калькулятора атрибутом (упрощенным как). `OperationContract`

## <a name="next-steps"></a>Дальнейшие действия

В этом руководстве вы узнали, как выполнять следующие задачи:
> [!div class="checklist"]
>
> - Создайте проект библиотеки обслуживания WCF.
> - Определите интерфейс контракта на обслуживание.

Перейти к следующему учебнику, чтобы узнать, как реализовать контракт на обслуживание WCF.

> [!div class="nextstepaction"]
> [Учебник: Реализация контракта на обслуживание WCF](how-to-implement-a-wcf-contract.md)
