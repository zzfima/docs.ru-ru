---
title: Интеграция WPF и WF в XAML
ms.date: 03/30/2017
ms.assetid: a4f53b48-fc90-4315-bca0-ba009562f488
ms.openlocfilehash: b8015e5c526f58875beb58ab48a21c050bdc8a06
ms.sourcegitcommit: 42ed59871db1f29a32b3d8e7abeb20e6eceeda7c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2019
ms.locfileid: "74960087"
---
# <a name="wpf-and-windows-workflow-foundation-integration-in-xaml"></a>Интеграция WPF и Windows Workflow Foundation в XAML

В этом примере показано, как создать приложение, которое использует функции Windows Presentation Foundation (WPF) и Windows Workflow Foundation (WF) в одном документе XAML. Для этого в образце используется Windows Workflow Foundation и расширяемость XAML.

## <a name="sample-details"></a>Подробные сведения об образце

 Файл ShowWindow.xaml десериализуется в действие <xref:System.Activities.Statements.Sequence> с двумя строковыми переменными, которыми управляют действия последовательности: `ShowWindow` и `WriteLine`. Действие <xref:System.Activities.Statements.WriteLine> выводит в окно консоли выражение, которое оно назначает свойству <xref:System.Activities.Statements.WriteLine.Text%2A>. `ShowWindow` действие отображает окно WPF в рамках логики выполнения. Контекст <xref:System.Activities.ActivityContext.DataContext%2A> окна включает переменные, объявленные в последовательности. В элементах управления окна, объявленных в действии `ShowWindow`, используется привязка данных для управления этими переменными. Наконец, окно содержит элемент управления "Кнопка". Событие `Click` для кнопки обрабатывается с помощью <xref:System.Activities.ActivityDelegate> с именем `MarkupExtension`, содержащего действие `CloseWindow`. `MarkUpExtension` вызывает содержащееся действие, которое предоставляет в качестве контекста любые объекты, обозначенные `x:Name`, а также <xref:System.Activities.ActivityContext.DataContext%2A> содержащего окна. Таким образом, окно `CloseWindow.InArgument<Window>` может быть привязано с использованием выражения, которое ссылается на имя окна.

 `ShowWindow` действие является производным от класса <xref:System.Activities.AsyncCodeActivity%601> для вывода окна WPF и завершается при закрытии окна. Свойство `Window` имеет тип `Func<Window>`, который позволяет создавать окно по запросу для каждого выполнения действия. Свойство `Window` использует <xref:System.Xaml.XamlDeferringLoader> для включения этой модели отсроченной оценки. Загрузчик `FuncFactoryDeferringLoader` позволяет перехватывать модуль `XamlReader` в течение сериализации, а затем выполнять чтение в ходе выполнения действия.

 Правильно запрограммированное действие никогда не блокирует поток-планировщик. Однако действие `ShowWindow` не может завершиться, пока окно, в котором оно отображается, не будет закрыто. Действие `ShowWindow` достигает этого поведения следующим образом: оно порождается от <xref:System.Activities.AsyncCodeActivity>, вызывает метод <xref:System.Activities.WorkflowInvoker.BeginInvoke%2A> в методе <xref:System.Activities.AsyncCodeActivity.BeginExecute%2A> и отображает модальное окно. Делегат вызывается с помощью WPF <xref:System.ServiceModel.InstanceContext.SynchronizationContext%2A>. Активность `ShowWindow` назначает свойство <xref:System.Activities.ActivityContext.DataContext%2A> свойству `Window.DataContext` для обеспечения доступа любым связанным элементам управления данных к переменным в области.

 Последняя особенность, представляющая интерес в этом образце, состоит в том, что расширение <xref:System.Workflow.ComponentModel.Serialization.MarkupExtension> вызывается расширением `DelegateActivityExtension`. Метод `ProvideValue` этого расширения разметки возвращает делегат, который вызывает внедренное действие. Это действие выполняется в среде, которая включает в себя контекст данных WPF и все `x:Name` значения в области. В методе `GenericInvoke` эта среда предоставляется действию через расширение <xref:System.Activities.Hosting.SymbolResolver>. Это расширение добавляется к объекту <xref:System.Activities.WorkflowInvoker>, который затем используется для вызова внедренного действия при каждом вызове делегата расширения разметки.

> [!NOTE]
> Конструктор по умолчанию не поддерживает действие ShowWindow. Файл ShowWindow.Xaml как таковой не отображается правильно в конструкторе.

## <a name="run-the-sample"></a>Запустить образец

1. С помощью Visual Studio откройте файл решения Впфвфинтегратион. sln.

2. Чтобы построить решение, нажмите клавиши **Ctrl**+**SHIFT**+**B**.

3. Чтобы запустить решение, нажмите клавишу **F5**.

4. Введите свои имя и фамилию в диалоговом окне.

5. Закройте диалоговое окно, и консоль выполнит эхо-повтор вашего имени.

> [!IMPORTANT]
> Образцы уже могут быть установлены на компьютере. Перед продолжением проверьте следующий каталог (по умолчанию).
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> Если этот каталог не существует, перейдите к [примерам Windows Communication Foundation (WCF) и Windows Workflow Foundation (WF) для .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) , чтобы скачать все Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Samples. Этот образец расположен в следующем каталоге.
>
> `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\WPFWFIntegration`
