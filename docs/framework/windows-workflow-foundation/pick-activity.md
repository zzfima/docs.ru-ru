---
title: Действие Pick
ms.date: 03/30/2017
ms.assetid: b3e49b7f-0285-4720-8c09-11ae18f0d53e
ms.openlocfilehash: 672de5fd3df5e8dde6c54118503bf2a11353b116
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182894"
---
# <a name="pick-activity"></a>Действие Pick
Действие <xref:System.Activities.Statements.Pick> позволяет упростить моделирование набора триггеров событий, а затем соответствующих обработчиков.  Действие содержит <xref:System.Activities.Statements.Pick> коллекцию действий <xref:System.Activities.Statements.PickBranch>, в которой все элементы <xref:System.Activities.Statements.PickBranch> являются парами, состоящими из действия <xref:System.Activities.Statements.PickBranch.Trigger%2A> и действия <xref:System.Activities.Statements.PickBranch.Action%2A>.  Во время выполнения триггеры для всех ветвей выполняются параллельно.  Когда срабатывает один триггер, выполняется соответствующее действие, а остальные триггеры отменяются.  Поведение [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] <xref:System.Activities.Statements.Pick> действия аналогично деятельности .NET Framework 3.5. <xref:System.Workflow.Activities.ListenActivity>  
  
 На следующем снимке экрана из примера пакета SDK [Использование действия Pick](./samples/using-the-pick-activity.md) показано действие Pick с двумя ветвями.  В одной ветви есть триггер с именем **Read input** — настраиваемое действие, считывающее входные данные из командной строки. Во второй ветви имеется триггер действия <xref:System.Activities.Statements.Delay>. Если активность **ввода Чтения** получает <xref:System.Activities.Statements.Delay> данные <xref:System.Activities.Statements.Delay> до завершения действия, задержка будет отменена, а приветствие будет записано на консоль.  В противном случае, если действие **Read input** не получает данные в отведенное время, это действие отменяется, и в консоль выводится сообщение об окончании времени ожидания.  Это стандартный прием для добавления периода времени ожидания к любому действию.  
  
 ![Действие Pick](./media/pick-activity/pick-activity-two-branches.jpg)  
  
## <a name="best-practices"></a>Рекомендации  
 При использовании действия Pick выполняемой ветвью действия становится ветвь, триггеры которой первыми завершат выполнение.  Теоретически, все триггеры выполняются параллельно, и один триггер может выполнить большую часть свой логики до того, как будет отменен из-за завершения работы другого.  С учетом этого необходимо соблюдать следующие инструкции при работе с действием Pick: работать с триггером, как если бы он представлял одно событие, и помещать в него минимально возможный объем логики.  В идеале триггер должен содержать объем логики, достаточный лишь для получения события, и обработка этого события должна выполняться в действии этой ветви.  Этот метод минимизирует объем перекрытия при выполнении триггеров.  Для примера можно представить <xref:System.Activities.Statements.Pick> с двумя триггерами, где каждый триггер содержит действие <xref:System.ServiceModel.Activities.Receive> с дополнительной логикой.  Если дополнительная логика представляет точку бездействия, то существует вероятность успешного завершения обоих действий <xref:System.ServiceModel.Activities.Receive>.  Один триггер будет полностью выполнен, а второй будет выполнен частично.  В определенных ситуациях принятие сообщения и последующее частичное выполнение его обработки недопустимо.  Следовательно, что касается применения таких встроенных действий обмена сообщениями WF, как <xref:System.ServiceModel.Activities.Receive> и <xref:System.ServiceModel.Activities.SendReply>, то <xref:System.ServiceModel.Activities.Receive> часто используется в триггерах, а <xref:System.ServiceModel.Activities.SendReply> и другая логика должны быть при любой возможности помещены в действие.  
  
## <a name="using-the-pick-activity-in-the-designer"></a>Использование действия Pick в конструкторе  
 Чтобы использовать Pick в конструкторе, найдите **Pick** и **PickBranch** на панели элементов.  Перетащите **Pick** на холст.  По умолчанию новое действие **Pick** в конструкторе будет содержать две ветви.  Чтобы добавить дополнительные ветви, перетащите действие **PickBranch** в область рядом с существующими ветвями. Действия можно перетаскивать в действие **Pick** в области **Trigger** или область **Action** любого действия **PickBranch**.  
  
## <a name="using-the-pick-activity-in-code"></a>Использование действия Pick в коде  
 Действие <xref:System.Activities.Statements.Pick> используется при заполнении его коллекции <xref:System.Activities.Statements.Pick.Branches%2A> действиями <xref:System.Activities.Statements.PickBranch>. Все действия <xref:System.Activities.Statements.PickBranch> имеют свойство <xref:System.Activities.Statements.PickBranch.Trigger%2A> типа <xref:System.Activities.Activity>. После завершения выполнения указанного действия выполняется <xref:System.Activities.Statements.PickBranch.Action%2A>.  
  
 В следующем примере кода показано использование действия <xref:System.Activities.Statements.Pick> для реализации времени ожидания для действия, которое считывает строку с консоли.  
  
```csharp  
Sequence body = new Sequence()  
{  
    Variables = { name },  
    Activities =
   {  
       new System.Activities.Statements.Pick  
        {  
           Branches =
           {  
               new PickBranch  
               {  
                   Trigger = new ReadLine  
                   {  
                      Result = name,  
                      BookmarkName = "name"  
                   },  
                   Action = new WriteLine
                   {
                       Text = ExpressionServices.Convert<string>(ctx => "Hello " +
                           name.Get(ctx))
                   }  
               },  
               new PickBranch  
               {  
                   Trigger = new Delay  
                   {  
                      Duration = new TimeSpan(0, 0, 5)  
                   },  
                   Action = new WriteLine  
                   {  
                      Text = "Time is up."  
                   }  
               }  
           }  
       }  
   }  
};  
```  
  
```xaml  
<Sequence xmlns="http://schemas.microsoft.com/netfx/2009/xaml/activities" xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml">  
  <Sequence.Variables>  
    <Variable x:TypeArguments="x:String" Name="username" />  
  </Sequence.Variables>  
  <Pick>  
    <PickBranch>  
      <PickBranch.Trigger>  
        <ReadLine BookmarkName="name" Result="username" />  
      </PickBranch.Trigger>  
      <WriteLine>[String.Concat("Hello ", username)]</WriteLine>  
    </PickBranch>  
    <PickBranch>  
      <PickBranch.Trigger>  
        <Delay>00:00:05</Delay>  
      </PickBranch.Trigger>  
      <WriteLine>Time is up.</WriteLine>  
    </PickBranch>  
  </Pick>  
</Sequence>  
```
