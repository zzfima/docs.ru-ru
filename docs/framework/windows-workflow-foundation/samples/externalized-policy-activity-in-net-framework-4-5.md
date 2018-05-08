---
title: Реализованное действие политики в .NET Framework 4.5
ms.date: 03/30/2017
ms.assetid: 92fd6f92-23a1-4adf-b96a-2754ea93ad3e
ms.openlocfilehash: 1d163659fa4b04694d9c97087f67fcd0713b56aa
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="externalized-policy-activity-in-net-framework-45"></a>Реализованное действие политики в .NET Framework 4.5
В этом примере демонстрируется, как действия ExternalizedPolicy4 можно выполнять существующие [!INCLUDE[netfx35_long](../../../../includes/netfx35-long-md.md)] Windows Workflow Foundation (WF 3.5) <xref:System.Workflow.Activities.Rules.RuleSet> объекты в [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)] Windows Workflow Foundation (WF 4.5) непосредственно с помощью модуля правил поставляется в WF 3.5. Используя это действие, можно создавать и выполнять любой существующий набор правил <xref:System.Workflow.Activities.Rules.RuleSet> WF 3.5. Дополнительные сведения об обработчике правил WF 3.5, входящей в состав Windows Workflow Foundation [введение в обработчик правил Windows Workflow Foundation](http://go.microsoft.com/fwlink/?LinkId=166079). Дополнительные сведения о миграции правил [!INCLUDE[wf1](../../../../includes/wf1-md.md)] в [!INCLUDE[netfx_current_short](../../../../includes/netfx-current-short-md.md)], прочитайте руководство по миграции на [руководство по миграции](../../../../docs/framework/windows-workflow-foundation/migration-guidance.md).  
  
## <a name="projects-in-this-sample"></a>Проекты в этом образце  
  
|Имя проекта|Описание|Основные файлы|  
|-|-|-|  
|ExternalizedPolicy4|Содержит действие PolicyExternalizedPolicy4 и его конструктор WF 4.5.|**ExternalizedPolicy4.cs**: определение действия.<br /><br /> **ExternalizedPolicy4Designer.xaml**: пользовательский конструктор действия ExternalizedPolicy4. Он использует редактор правил (<xref:System.Workflow.Activities.Rules.Design.RuleSetDialog>), определенный в конструкторе правил WF 3.5.|  
|ImperativeCodeClientSample|Образец клиентского приложения, осуществляющего конфигурирование и запуск рабочего процесса с использованием приложения PolicyExternalizedPolicy4, использующего императивный код C# (конструктор не используется).|**ApplyDiscount.rules**: файл с [!INCLUDE[wf1](../../../../includes/wf1-md.md)] определениями правил.<br /><br /> **Order.cs**: тип, представляющий заказ клиента. Правила применяются к объектам этого типа.<br /><br /> **Program.cs**: настраивает и запускает рабочий процесс с действием policy4 для применения правил, определенных в ApplyDiscount.rules, к экземплярам объектов Order.<br /><br /> App.config: файл конфигурации, содержащий путь к файлу правил.|  
|DesignerClientSample|Образец клиентского приложения, осуществляющего конфигурирование и запуск рабочего процесса с использованием приложения ExternalPolicy4 в конструкторе [!INCLUDE[wf1](../../../../includes/wf1-md.md)].|**Sequence1.XAML**: последовательный рабочий процесс, использующий действие Policy4 для проверки правил.<br /><br /> **Program.cs**: выполняет экземпляр рабочего процесса, определенного в Sequence1.xaml.|  
  
## <a name="the-externalizedpolicy4-activity"></a>Действие ExternalizedPolicy4  
 Действие ExternalizedPolicy4 представляет собой действие <xref:System.Activities.NativeActivity>, позволяющее выполнять объекты WF 3.5 <xref:System.Workflow.Activities.Rules.RuleSet> в рамках рабочих процессов WF 4.5. Следующий пример кода представляет собой упрощенное определение публичной объектной модели действия.  
  
```  
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
  
|Свойство|Описание|  
|-|-|  
|RuleSetFilePath|Путь к файлу <xref:System.Workflow.Activities.Rules.RuleSet> в .NET Framework 3.5, который определяется при выполнении действия.|  
|RuleSetName|Имя <xref:System.Workflow.Activities.Rules.RuleSet>, которое будет использоваться в файлах правил с расширением RULES.|  
|TargetObject|Объект, для которого рассчитываются объекты <xref:System.Workflow.Activities.Rules.Rule> в <xref:System.Workflow.Activities.Rules.RuleSet>.|  
|ResultObject|Результирующий объект, полученный после применения правил (например, правил, примененных к входному аргументу), с сохранением результата в результирующем аргументе.|  
|ValidationError|Список ошибок проверки, возвращаемый обработчиком правил WF 3.5 при проверке класса <xref:System.Workflow.Activities.Rules.RuleSet> для целевого объекта до его выполнения.|  
  
## <a name="externalizedpolicy4-activity-designer"></a>Конструктор действия ExternalizedPolicy4  
 Конструктор действия ExternalizedPolicy4 позволяет конфигурировать активность таким образом, чтобы использовать существующий набор правил без необходимости написания кода. Достаточно просто задать путь к файлу с расширением RULES и указать желаемое имя <xref:System.Workflow.Activities.Rules.RuleSet>. Конструктор также позволяет вносить изменения в <xref:System.Workflow.Activities.Rules.RuleSet>. После построения решения действие будет занесено в область элементов в раздел Microsoft.Samples.Activities.Rules. Конструктор позволяет выбирать файл с расширением RULES и <xref:System.Workflow.Activities.Rules.RuleSet>. Когда **изменить набор правил** кнопки, WF 3.5 <xref:System.Workflow.Activities.Rules.Design.RuleSetDialog> отображается. Это диалоговое окно представляет собой повторно размещенный редактор правил WF 3.5, используемый для просмотра и изменения правил, выполняемых действием ExternalizedPolicy4.  
  
## <a name="policy4-and-externalpolicy4"></a>Policy4 и ExternalPolicy4  
 [Действие политики в .NET Framework 4.5](../../../../docs/framework/windows-workflow-foundation/samples/policy-activity-in-net-framework-4-5.md) действие позволяет создавать и выполнять .NET Framework 3.5 RuleSet в рабочий процесс WF 4.5. Набор правил <xref:System.Workflow.Activities.Rules.RuleSet> сериализуется в рамках определения действия Policy4 в языке XAML. Образец действия ExternalizedPolicy4 показывает, как использовать существующий внешний набор правил <xref:System.Workflow.Activities.Rules.RuleSet> (содержащийся в файле с расширением RULES).  
  
## <a name="using-this-sample"></a>Использование этого образца  
 Для запуска этого образца специальные настройки не требуются. Откройте решение в среде [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] и нажмите клавишу F5 для запуска приложения.  
  
 Этот образец содержит два клиентских приложения: ImperativeCodeClientSample и DesignerClientSample. Клиентское приложение ImperativeCodeClientSample показывает, как конфигурировать и запускать действие ExternalizedPolicy4 с использованием императивного кода C#. Клиентское приложение DesignerClientSample показывает, как конфигурировать и запускать действие ExternalizedPolicy4 с использованием конструктора.  
  
#### <a name="to-run-the-imperativecodeclientsample-application"></a>Запуск клиентского приложения ImperativeCodeClientSample  
  
1.  Откройте файл решения Policy4sample.sln в среде [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)].  
  
2.  В **обозревателе решений**, щелкните правой кнопкой мыши **ImperativeCodeClientSample** проекта, а затем выберите **Назначить запускаемым проектом**.  
  
3.  Чтобы запустить проект, нажмите клавиши CTRL+F5.  
  
#### <a name="to-run-the-designerclientsample-application"></a>Нажмите клавишу F5, чтобы запустить приложение DesignerClientSample.  
  
1.  Откройте файл решения Policy4sample.sln в среде [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)].  
  
2.  В **обозревателе решений**, щелкните правой кнопкой мыши **DesignerClientSample** проекта, а затем выберите **Назначить запускаемым проектом**.  
  
3.  Чтобы скомпилировать проект, нажмите клавиши CTRL+SHIFT+B.  
  
4.  Нажмите клавиши CTRL+F5, чтобы запустить проект.  
  
> [!IMPORTANT]
>  Образцы уже могут быть установлены на компьютере. Перед продолжением проверьте следующий каталог (по умолчанию).  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Если этот каталог не существует, перейдите к [Windows Communication Foundation (WCF) и образцы Windows Workflow Foundation (WF) для .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) для загрузки всех Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] образцов. Этот образец расположен в следующем каталоге.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\ActivityLibrary\Rules-ExternalizedPolicy4`
