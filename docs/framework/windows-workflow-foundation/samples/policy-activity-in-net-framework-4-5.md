---
title: Действие политики в .NET Framework 4.5
ms.date: 03/30/2017
ms.assetid: 8e375e0c-d7c1-4d69-88ab-36d52db0aa7e
ms.openlocfilehash: 9d8983f2f1d3f75beffeacfff4b673f6c23c4204
ms.sourcegitcommit: 2350a091ef6459f0fcfd894301242400374d8558
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/21/2018
ms.locfileid: "46562272"
---
# <a name="policy-activity-in-net-framework-45"></a>Действие политики в .NET Framework 4.5
Действие Policy4 позволяет Windows Workflow Foundation в [!INCLUDE[netfx35_long](../../../../includes/netfx35-long-md.md)] (WF 3.5) <xref:System.Workflow.Activities.Rules.RuleSet> объектов для использования в Windows Workflow Foundation в [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)] (WF 4.5) непосредственно с помощью обработчика правил, входящий в комплект поставки WF 3.5. Используя это действие, можно создавать и выполнять наборы правил <xref:System.Workflow.Activities.Rules.RuleSet> WF 3.5. Дополнительные сведения о обработчик правил WF 3.5, являющемся частью Windows Workflow Foundation см. Введение в обработчик правил Windows Workflow Foundation. Дополнительные сведения о миграции правил WF в [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)], см. в статье [руководство по миграции](../../../../docs/framework/windows-workflow-foundation/migration-guidance.md).  
  
> [!IMPORTANT]
>  Образцы уже могут быть установлены на компьютере. Перед продолжением проверьте следующий каталог (по умолчанию).  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Если этот каталог не существует, перейдите к [Windows Communication Foundation (WCF) и образцы Windows Workflow Foundation (WF) для .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) для загрузки всех Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] примеры. Этот образец расположен в следующем каталоге.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\ActivityLibrary\Rules-Policy4`  
  
## <a name="projects-in-this-sample"></a>Проекты в этом образце  
  
|Имя проекта|Описание|Основные файлы|  
|------------------|-----------------|----------------|  
|Policy4|Содержит действие Policy4 и его конструктор в [!INCLUDE[wf1](../../../../includes/wf1-md.md)].|**Policy4.cs**: определение действия Policy4.<br /><br /> **PolicyDesigner.xaml**: пользовательский конструктор действия Policy4. Он использует редактор правил ([класс RuleSetDialog](https://go.microsoft.com/fwlink/?LinkId=150378)) из [!INCLUDE[wf1](../../../../includes/wf1-md.md)] обработчик правил.|  
|ImperativeCodeClientSample|Образец клиентского приложения, осуществляющего конфигурирование и запуск рабочего процесса при помощи приложения Policy4, использующего императивный код C# (конструктор [!INCLUDE[wf1](../../../../includes/wf1-md.md)] не используется).|**ApplyDiscount.rules**: файл с [!INCLUDE[wf1](../../../../includes/wf1-md.md)] определениями правил.<br /><br /> **Order.cs**: тип, представляющий заказ клиента. Правила применяются к объектам этого типа.<br /><br /> **Program.cs**: настраивает и запускает рабочий процесс с действием Policy4 для применения правил, определенных в ApplyDiscount.rules, к экземплярам объектов Order.<br /><br /> **App.config**: файл конфигурации, содержащий путь к файлу правил.|  
|DesignerClientSample|Образец клиентского приложения, осуществляющего конфигурирование и запуск рабочего процесса в конструкторе [!INCLUDE[wf1](../../../../includes/wf1-md.md)].|**Sequence1.XAML**: последовательный рабочий процесс, использующий действие Policy4 для проверки правил.<br /><br /> `Program.cs`: выполняет экземпляр рабочего процесса, определенного в Sequence1.xaml.|  
  
## <a name="the-policy4-activity"></a>Действие Policy4  
 Действие Policy4 представляет собой производный от <xref:System.Activities.NativeActivity%601> класс, позволяющий рабочим процессам выполнять наборы правил [!INCLUDE[wf1](../../../../includes/wf1-md.md)]. Следующий пример кода представляет собой упрощенное определение публичной объектной модели действия.  
  
```csharp  
public class Policy4Activity<TResult>: NativeActivity<TResult>  
{  
    public RuleSet RuleSet  
  
    [IsRequired]  
    public InArgument Input  
  
    public OutArgument<ValidationErrorCollection> ValidationErrors  
}  
```  
  
|Свойство|Описание|  
|--------------|-----------------|  
|RuleSet|WF [RuleSet Class](https://go.microsoft.com/fwlink/?LinkId=150379) для .NET Framework 3.5 следует вычислить во время выполнения действия.|  
|TargetObject|Объект, по которому правила в [RuleSet Class](https://go.microsoft.com/fwlink/?LinkId=150379) вычисляются.|  
|ValidationError|Список ошибок проверки, возвращаемый [!INCLUDE[wf1](../../../../includes/wf1-md.md)] обработчик правил для .NET Framework 3.5 при проверке [RuleSet Class](https://go.microsoft.com/fwlink/?LinkId=150379) целевого объекта перед выполнением.|  
  
## <a name="policy4-activity-designer"></a>Конструктор действия Policy4  
 Конструктор действия Policy4 добавляет возможность конфигурирования действия Policy4 без необходимости написания кода. После построения решения, его можно найти на панели элементов в разделе **Microsoft.Samples.Activities.Rules**.  
  
 В среде проектирования WF Designer можно конфигурировать целевой объект и набор правил. Когда **Edit RuleSet** кнопки, WF [класс RuleSetDialog](https://go.microsoft.com/fwlink/?LinkId=150378) для [!INCLUDE[netfx35_short](../../../../includes/netfx35-short-md.md)] отображается. Открытие этого диалогового окна означает повторное размещение редактора правил [!INCLUDE[netfx35_short](../../../../includes/netfx35-short-md.md)]. Редактор используется для создания и изменения правил, выполняемых действием Policy4.  
  
## <a name="using-this-sample"></a>Использование этого образца  
 Для запуска этого образца применение специальных наборов правил не требуется. Достаточно открыть решение в Visual Studio и нажать клавишу F5 для запуска приложения.  
  
 Этот образец содержит два клиентских приложения: ImperativeCodeClientSample и DesignerClientSample. Клиентское приложение ImperativeCodeClientSample показывает, как конфигурировать и запускать действие Policy40 с использованием императивного кода C#. Клиентское приложение DesignerClientSample показывает, как конфигурировать и запускать действие Policy4 с использованием конструктора.  
  
#### <a name="to-run-the-imperativecodeclientsample-client-application"></a>Запуск клиентского приложения ImperativeCodeClientSample  
  
1.  Откройте файл решения Policy4Sample.sln в среде [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)].  
  
2.  В **обозревателе решений**, щелкните правой кнопкой мыши **ImperativeCodeClientSample** проекта, а затем выберите **Назначить запускаемым проектом**.  
  
3.  Чтобы запустить проект, нажмите клавиши CTRL+F5.  
  
#### <a name="to-run-the-imperativecodeclientsample-client-application"></a>Запуск клиентского приложения ImperativeCodeClientSample  
  
1.  Откройте файл решения Policy4Sample.sln в среде [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)].  
  
2.  В **обозревателе решений**, щелкните правой кнопкой мыши **DesignerClientSample** проекта.  
  
    -   Выберите **Назначить запускаемым проектом**.  
  
3.  Чтобы скомпилировать проект, нажмите сочетание клавиш CTRL+SHIFT+B.  
  
4.  Чтобы запустить проект, нажмите клавиши CTRL+F5.