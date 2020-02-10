---
title: Реализованное действие политики в .NET Framework 4.5
ms.date: 03/30/2017
ms.assetid: 92fd6f92-23a1-4adf-b96a-2754ea93ad3e
ms.openlocfilehash: 8fd08c9c29f7a268170aaa101a9bdb85250157dc
ms.sourcegitcommit: 011314e0c8eb4cf4a11d92078f58176c8c3efd2d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/09/2020
ms.locfileid: "77094635"
---
# <a name="externalized-policy-activity-in-net-framework-45"></a>Реализованное действие политики в .NET Framework 4.5

В этом примере показано, как действие ExternalizedPolicy4 разрешает выполнение существующих .NET Framework 3,5 Windows Workflow Foundation (WF 3,5) <xref:System.Workflow.Activities.Rules.RuleSet> объектов [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)] Windows Workflow Foundation (WF 4,5) непосредственно с помощью обработчика правил, который поставляется в WF 3,5. Используя это действие, можно создавать и выполнять любой существующий набор правил <xref:System.Workflow.Activities.Rules.RuleSet> WF 3.5. Дополнительные сведения о обработчике правил WF 3,5, включенном в состав Windows Workflow Foundation, см. в статье [Введение в обработчик правил Windows Workflow Foundation](https://docs.microsoft.com/previous-versions/dotnet/articles/aa480193(v=msdn.10)). Дополнительные сведения о переносе правил в [!INCLUDE[wf1](../../../../includes/wf1-md.md)] в [!INCLUDE[netfx_current_short](../../../../includes/netfx-current-short-md.md)]см. в [руководстве по миграции](../migration-guidance.md).

## <a name="projects-in-this-sample"></a>Проекты в этом образце

|Имя проекта|Description|Основные файлы|
|-|-|-|
|ExternalizedPolicy4|Содержит действие PolicyExternalizedPolicy4 и его конструктор WF 4.5.|**ExternalizedPolicy4.CS**: определение действия.<br /><br /> **ExternalizedPolicy4Designer. XAML**: Пользовательский конструктор для действия ExternalizedPolicy4. Он использует редактор правил (<xref:System.Workflow.Activities.Rules.Design.RuleSetDialog>), определенный в конструкторе правил WF 3.5.|
|ImperativeCodeClientSample|Образец клиентского приложения, осуществляющего конфигурирование и запуск рабочего процесса с использованием приложения PolicyExternalizedPolicy4, использующего императивный код C# (конструктор не используется).|**ApplyDiscount. rules**: файл с определениями правил [!INCLUDE[wf1](../../../../includes/wf1-md.md)].<br /><br /> **Order.CS**: тип, представляющий заказ клиента. Правила применяются к объектам этого типа.<br /><br /> **Program.CS**: настраивает и запускает рабочий процесс с действием Policy4 для применения правил, определенных в ApplyDiscount. rules к экземплярам объектов Order.<br /><br /> App.config: файл конфигурации, содержащий путь к файлу правил.|
|DesignerClientSample|Образец клиентского приложения, осуществляющего конфигурирование и запуск рабочего процесса с использованием приложения ExternalPolicy4 в конструкторе [!INCLUDE[wf1](../../../../includes/wf1-md.md)].|**Sequence1. XAML**: последовательный рабочий процесс, использующий действие Policy4 для выполнения оценки правил.<br /><br /> **Program.CS**: запускает экземпляр рабочего процесса, определенный в Sequence1. XAML.|

## <a name="the-externalizedpolicy4-activity"></a>Действие ExternalizedPolicy4

Действие ExternalizedPolicy4 представляет собой действие <xref:System.Activities.NativeActivity>, позволяющее выполнять объекты WF 3.5 <xref:System.Workflow.Activities.Rules.RuleSet> в рамках рабочих процессов WF 4.5. Следующий пример кода представляет собой упрощенное определение публичной объектной модели действия.

```csharp
public class ExternalizedPolicy4Activity<TResult>: CodeActivity
{
    public string RulesFilePath

    public string RuleSetName

    [RequiredArgument]
    public InArgument<T> TargetObject

    [RequiredArgument]
    public OutArgument<T> ResultObject

    public OutArgument<ValidationErrorCollection> ValidationErrors
}
```

|Свойство|Description|
|-|-|
|RuleSetFilePath|Путь к файлу <xref:System.Workflow.Activities.Rules.RuleSet> в .NET Framework 3.5, который определяется при выполнении действия.|
|RuleSetName|Имя <xref:System.Workflow.Activities.Rules.RuleSet>, которое будет использоваться в файлах правил с расширением RULES.|
|TargetObject|Объект, для которого рассчитываются объекты <xref:System.Workflow.Activities.Rules.Rule> в <xref:System.Workflow.Activities.Rules.RuleSet>.|
|ResultObject|Результирующий объект, полученный после применения правил (например, правил, примененных к входному аргументу), с сохранением результата в результирующем аргументе.|
|ValidationError|Список ошибок проверки, возвращаемый обработчиком правил WF 3.5 при проверке класса <xref:System.Workflow.Activities.Rules.RuleSet> для целевого объекта до его выполнения.|

## <a name="externalizedpolicy4-activity-designer"></a>Конструктор действия ExternalizedPolicy4

Конструктор действия ExternalizedPolicy4 позволяет конфигурировать активность таким образом, чтобы использовать существующий набор правил без необходимости написания кода. Достаточно просто задать путь к файлу с расширением RULES и указать желаемое имя <xref:System.Workflow.Activities.Rules.RuleSet>. Конструктор также позволяет вносить изменения в <xref:System.Workflow.Activities.Rules.RuleSet>. После построения решения действие будет занесено в область элементов в раздел Microsoft.Samples.Activities.Rules. Конструктор позволяет выбирать файл с расширением RULES и <xref:System.Workflow.Activities.Rules.RuleSet>. При нажатии кнопки **изменить набор правил** отображается <xref:System.Workflow.Activities.Rules.Design.RuleSetDialog> WF 3,5. Это диалоговое окно представляет собой повторно размещенный редактор правил WF 3.5, используемый для просмотра и изменения правил, выполняемых действием ExternalizedPolicy4.

## <a name="policy4-and-externalpolicy4"></a>Policy4 и ExternalPolicy4

Действие политики позволяет создавать и выполнять .NET Framework 3,5 RuleSet в рабочем процессе WF 4,5. Набор правил <xref:System.Workflow.Activities.Rules.RuleSet> сериализуется в рамках определения действия Policy4 в языке XAML. Образец действия ExternalizedPolicy4 показывает, как использовать существующий внешний набор правил <xref:System.Workflow.Activities.Rules.RuleSet> (содержащийся в файле с расширением RULES).

## <a name="use-this-sample"></a>Используйте этот пример

Для запуска этого образца специальные настройки не требуются. Откройте решение в Visual Studio и нажмите клавишу **F5** , чтобы запустить приложение.

Этот образец содержит два клиентских приложения: ImperativeCodeClientSample и DesignerClientSample. Клиентское приложение ImperativeCodeClientSample показывает, как конфигурировать и запускать действие ExternalizedPolicy4 с использованием императивного кода C#. Клиентское приложение DesignerClientSample показывает, как конфигурировать и запускать действие ExternalizedPolicy4 с использованием конструктора.

### <a name="run-the-imperativecodeclientsample-application"></a>Запуск приложения Императивекодеклиентсампле

1. С помощью Visual Studio откройте файл решения *Policy4sample. sln* .

2. В **Обозреватель решений**щелкните правой кнопкой мыши проект **Императивекодеклиентсампле** и выберите **Назначить запускаемым проектом**.

3. Чтобы запустить проект, нажмите клавиши **Ctrl**+**F5**.

### <a name="run-the-designerclientsample-application"></a>Запуск приложения Десигнерклиентсампле

1. С помощью Visual Studio откройте файл решения *Policy4sample. sln* .

2. В **Обозреватель решений**щелкните правой кнопкой мыши проект **Десигнерклиентсампле** и выберите **Назначить запускаемым проектом**.

3. Нажмите клавиши **Ctrl**+**SHIFT**+**B** , чтобы скомпилировать проект.

4. Нажмите клавиши **Ctrl**+**F5** , чтобы запустить проект.

> [!IMPORTANT]
> Образцы уже могут быть установлены на компьютере. Перед продолжением проверьте следующий каталог (по умолчанию).
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> Если этот каталог не существует, перейдите к [примерам Windows Communication Foundation (WCF) и Windows Workflow Foundation (WF) для .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) , чтобы скачать все Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Samples.
>
> Этот образец находится в следующем каталоге:
>
> `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\ActivityLibrary\Rules-ExternalizedPolicy4`
