---
title: Интеграция WPF и WF в XAML
ms.date: 03/30/2017
ms.assetid: a4f53b48-fc90-4315-bca0-ba009562f488
ms.openlocfilehash: 188702cfc13d7e353238e108066cc3d5f1c8bda9
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59298647"
---
# <a name="wpf-and-wf-integration-in-xaml"></a>Интеграция WPF и WF в XAML
В этом примере показано, как создать приложение, использующее функции Windows Presentation Foundation (WPF) и Windows Workflow Foundation (WF) в одном документе XAML. Для этого в образце используется расширяемость Windows Workflow Foundation (WF) и XAML.

## <a name="sample-details"></a>Подробные сведения об образце
 Файл ShowWindow.xaml десериализуется в действие <xref:System.Activities.Statements.Sequence> с двумя строковыми переменными, которыми управляют действия последовательности: `ShowWindow` и `WriteLine`. Действие <xref:System.Activities.Statements.WriteLine> выводит в окно консоли выражение, которое оно назначает свойству <xref:System.Activities.Statements.WriteLine.Text%2A>. Действие `ShowWindow` отображает окно [!INCLUDE[avalon2](../../../../includes/avalon2-md.md)] как часть его логики выполнения. Контекст <xref:System.Activities.ActivityContext.DataContext%2A> окна включает переменные, объявленные в последовательности. В элементах управления окна, объявленных в действии `ShowWindow`, используется привязка данных для управления этими переменными. Наконец окно содержит элемент управления button. Событие `Click` для кнопки обрабатывается с помощью <xref:System.Activities.ActivityDelegate> с именем `MarkupExtension`, содержащего действие `CloseWindow`. `MarkUpExtension` вызывает содержащееся действие, которое предоставляет в качестве контекста любые объекты, обозначенные `x:Name`, а также <xref:System.Activities.ActivityContext.DataContext%2A> содержащего окна. Таким образом, окно `CloseWindow.InArgument<Window>` может быть привязано с использованием выражения, которое ссылается на имя окна.

 Действие `ShowWindow` порождается от класса <xref:System.Activities.AsyncCodeActivity%601> для отображения окна [!INCLUDE[avalon2](../../../../includes/avalon2-md.md)] и завершается при закрытии окна. Свойство `Window` имеет тип `Func<Window>`, который позволяет создавать окно по запросу для каждого выполнения действия. Свойство `Window` использует <xref:System.Xaml.XamlDeferringLoader> для включения этой модели отсроченной оценки. Загрузчик `FuncFactoryDeferringLoader` позволяет перехватывать модуль `XamlReader` в течение сериализации, а затем выполнять чтение в ходе выполнения действия.

 Правильно запрограммированное действие никогда не блокирует поток-планировщик. Однако действие `ShowWindow` не может завершиться, пока окно, в котором оно отображается, не будет закрыто. Действие `ShowWindow` достигает этого поведения следующим образом: оно порождается от <xref:System.Activities.AsyncCodeActivity>, вызывает метод <xref:System.Activities.WorkflowInvoker.BeginInvoke%2A> в методе <xref:System.Activities.AsyncCodeActivity.BeginExecute%2A> и отображает модальное окно. Делегат вызывается с помощью WPF <xref:System.ServiceModel.InstanceContext.SynchronizationContext%2A>. Активность `ShowWindow` назначает свойство <xref:System.Activities.ActivityContext.DataContext%2A> свойству `Window.DataContext` для обеспечения доступа любым связанным элементам управления данных к переменным в области.

 Последняя особенность, представляющая интерес в этом образце, состоит в том, что расширение <xref:System.Workflow.ComponentModel.Serialization.MarkupExtension> вызывается расширением `DelegateActivityExtension`. Метод `ProvideValue` этого расширения разметки возвращает делегат, который вызывает внедренное действие. Это действие эксплуатируется в среде, которая включает контекст данных [!INCLUDE[avalon2](../../../../includes/avalon2-md.md)] и любые значения `x:Name` в области. В методе `GenericInvoke` эта среда предоставляется действию через расширение <xref:System.Activities.Hosting.SymbolResolver>. Это расширение добавляется к объекту <xref:System.Activities.WorkflowInvoker>, который затем используется для вызова внедренного действия при каждом вызове делегата расширения разметки.

> [!NOTE]
>  Конструктор по умолчанию не поддерживает действие ShowWindow. Файл ShowWindow.Xaml как таковой не отображается правильно в конструкторе.

#### <a name="to-use-this-sample"></a>Использование этого образца

1. С помощью Visual Studio 2010, откройте файл решения WPFWFIntegration.sln.

2. Для построения решения нажмите CTRL+SHIFT+B.

3. Чтобы запустить решение, нажмите клавишу F5.

4. Введите свои имя и фамилию в диалоговом окне.

5. Закройте диалоговое окно, и консоль выполнит эхо-повтор вашего имени.

> [!IMPORTANT]
>  Образцы уже могут быть установлены на компьютере. Перед продолжением проверьте следующий каталог (по умолчанию).  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Если этот каталог не существует, перейдите к [Windows Communication Foundation (WCF) и образцы Windows Workflow Foundation (WF) для .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) для загрузки всех Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] примеры. Этот образец расположен в следующем каталоге.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\WPFWFIntegration`