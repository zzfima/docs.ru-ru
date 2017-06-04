---
title: "Действие политики в .NET Framework 4.5 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 8e375e0c-d7c1-4d69-88ab-36d52db0aa7e
caps.latest.revision: 15
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 15
---
# Действие политики в .NET Framework 4.5
Действие Policy4 позволяет использовать объекты [!INCLUDE[wf2](../../../../includes/wf2-md.md)] в [!INCLUDE[netfx35_long](../../../../includes/netfx35-long-md.md)] \(WF 3.5\) <xref:System.Workflow.Activities.Rules.RuleSet> в [!INCLUDE[wf2](../../../../includes/wf2-md.md)] непосредственно в [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)] \(WF 4.5\), применяя правила, установленные в WF 3.5.Используя это действие, можно создавать и выполнять наборы правил <xref:System.Workflow.Activities.Rules.RuleSet> WF 3.5.[!INCLUDE[crabout](../../../../includes/crabout-md.md)] об обработчике правил WF 3.5, являющемся частью Windows Workflow Foundation, см. в разделе «Введение в обработчик правил в Windows Workflow Foundation».Дополнительные сведения о правилах миграции на WF в [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)] см. в разделе [Руководство по миграции](../../../../docs/framework/windows-workflow-foundation//migration-guidance.md).  
  
> [!IMPORTANT]
>  Образцы уже могут быть установлены на компьютере.Перед продолжением проверьте следующий каталог \(по умолчанию\).  
>   
>  `<диск_установки>:\WF_WCF_Samples`  
>   
>  Если этот каталог не существует, перейдите на страницу [Образцы Windows Communication Foundation \(WCF\) и Windows Workflow Foundation \(WF\) для .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780), чтобы загрузить все образцы [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] и [!INCLUDE[wf1](../../../../includes/wf1-md.md)].Этот образец расположен в следующем каталоге.  
>   
>  `<диск_установки>:\WF_WCF_Samples\WF\Scenario\ActivityLibrary\Rules-Policy4`  
  
## Проекты в этом образце  
  
|Имя проекта|Описание|Основные файлы|  
|-----------------|--------------|--------------------|  
|Policy4|Содержит действие Policy4 и его конструктор в [!INCLUDE[wf1](../../../../includes/wf1-md.md)].|**Policy4.cs**: определение действия Policy4.<br /><br /> **PolicyDesigner.xaml**: пользовательский конструктор действия Policy4.Он использует редактор правил \([RuleSetDialog Class](http://go.microsoft.com/fwlink/?LinkId=150378)\), определенный в обработчике правил [!INCLUDE[wf1](../../../../includes/wf1-md.md)].|  
|ImperativeCodeClientSample|Образец клиентского приложения, осуществляющего конфигурирование и запуск рабочего процесса при помощи приложения Policy4, использующего императивный код C\# \(конструктор [!INCLUDE[wf1](../../../../includes/wf1-md.md)] не используется\).|**ApplyDiscount.rules**: Файл с определениями правил [!INCLUDE[wf1](../../../../includes/wf1-md.md)].<br /><br /> **Order.cs**: Тип, представляющий заказ клиента.Правила применяются к объектам этого типа.<br /><br /> **Program.cs**: Настраивает и запускает рабочий процесс с действием Policy4 для применения правил, определенных в ApplyDiscount.rules, к экземплярам объектов Order.<br /><br /> **App.config**: файл конфигурации, содержащий путь к файлу правил.|  
|DesignerClientSample|Образец клиентского приложения, осуществляющего конфигурирование и запуск рабочего процесса в конструкторе [!INCLUDE[wf1](../../../../includes/wf1-md.md)].|**Sequence1.xaml**: Последовательный рабочий процесс, использующий действие Policy4 для проверки правил.<br /><br /> `Program.cs`: выполняет экземпляр рабочего процесса, определенного в Sequence1.xaml.|  
  
## Действие Policy4  
 Действие Policy4 представляет собой производный от <xref:System.Activities.NativeActivity%601> класс, позволяющий рабочим процессам выполнять наборы правил [!INCLUDE[wf1](../../../../includes/wf1-md.md)].Следующий пример кода представляет собой упрощенное определение публичной объектной модели действия.  
  
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
|--------------|--------------|  
|RuleSet|Класс [RuleSet Class](http://go.microsoft.com/fwlink/?LinkId=150379) WF в .NET Framework 3.5 вычисляется после выполнения действия.|  
|TargetObject|Объект, для которого производится расчет правил в классе [RuleSet Class](http://go.microsoft.com/fwlink/?LinkId=150379).|  
|ValidationError|Список ошибок проверки, возвращаемый обработчиком правил [!INCLUDE[wf1](../../../../includes/wf1-md.md)] в .NET Framework 3.5 при проверке класса [RuleSet Class](http://go.microsoft.com/fwlink/?LinkId=150379) целевого объекта до его выполнения.|  
  
## Конструктор действия Policy4  
 Конструктор действия Policy4 добавляет возможность конфигурирования действия Policy4 без необходимости написания кода.После построения решения действие будет занесено в область элементов в раздел **Microsoft.Samples.Activities.Rules**.  
  
 В среде проектирования WF Designer можно конфигурировать целевой объект и набор правил.При нажатии кнопки **Edit RuleSet** будет выведен класс [RuleSetDialog Class](http://go.microsoft.com/fwlink/?LinkId=150378) WF для [!INCLUDE[netfx35_short](../../../../includes/netfx35-short-md.md)].Открытие этого диалогового окна означает повторное размещение редактора правил [!INCLUDE[netfx35_short](../../../../includes/netfx35-short-md.md)].Редактор используется для создания и изменения правил, выполняемых действием Policy4.  
  
## Использование этого образца  
 Для запуска этого образца применение специальных наборов правил не требуется.Достаточно открыть решение в Visual Studio и нажать клавишу F5 для запуска приложения.  
  
 Этот образец содержит два клиентских приложения: ImperativeCodeClientSample и DesignerClientSample.Клиентское приложение ImperativeCodeClientSample показывает, как конфигурировать и запускать действие Policy40 с использованием императивного кода C\#.Клиентское приложение DesignerClientSample показывает, как конфигурировать и запускать действие Policy4 с использованием конструктора.  
  
#### Запуск клиентского приложения ImperativeCodeClientSample  
  
1.  Откройте файл решения Policy4Sample.sln в среде [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)].  
  
2.  В окне **Обозреватель решений** щелкните правой кнопкой мыши проект **ImperativeCodeClientSample** и выберите команду **Назначить запускаемым проектом**.  
  
3.  Чтобы запустить проект, нажмите клавиши CTRL\+F5.  
  
#### Запуск клиентского приложения ImperativeCodeClientSample  
  
1.  Откройте файл решения Policy4Sample.sln в среде [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)].  
  
2.  В окне **Обозреватель решений** щелкните правой кнопкой мыши проект **DesignerClientSample**.  
  
    -   Выберите команду **Назначить запускаемым проектом**.  
  
3.  Чтобы скомпилировать проект, нажмите сочетание клавиш CTRL\+SHIFT\+B.  
  
4.  Чтобы запустить проект, нажмите клавиши CTRL\+F5.  
  
## См. также