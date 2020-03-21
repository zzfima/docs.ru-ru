---
title: Компенсация
ms.date: 03/30/2017
ms.assetid: 722e9766-48d7-456c-9496-d7c5c8f0fa76
ms.openlocfilehash: 75c5ed2f5e5c3a93834632ce499a2c8195fbc6bb
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79183004"
---
# <a name="compensation"></a>Компенсация
Компенсация в Фонде рабочего процесса Windows (WF) — это механизм, с помощью которого ранее выполненная работа может быть отменена или компенсирована (в соответствии с логикой, определенной приложением), когда происходит последующий сбой. В данном разделе описывается применение компенсации в рабочих процессах.  
  
## <a name="compensation-vs-transactions"></a>Сравнение компенсации и транзакций  
 Транзакция позволяет объединить несколько операций в одну единицу работы. Использование транзакции дает приложению возможность прерывать (откатывать) все изменения, выполненные в транзакции, если во время выполнения какой-либо части обработки транзакции возникнет ошибка. Однако использование транзакций может быть неприемлемо, если работа является долговременной. Пусть, например, приложение планирования путешествия реализовано как рабочий процесс. Шагами рабочего процесса могут быть заказ авиабилетов, ожидание подтверждения диспетчера и, наконец, оплата билета. Этот процесс может занять несколько дней, и включение шагов заказа и оплаты авиабилетов в одну транзакцию непрактично. Если позднее в процессе произойдет ошибка, в таком сценарии можно воспользоваться компенсацией для отмены шага заказа в рабочем процессе.  
  
> [!NOTE]
> В этом разделе описывается компенсация в рабочих процессах. Для получения дополнительной информации о транзакциях в рабочих процессах см. [Transactions](workflow-transactions.md) <xref:System.Activities.Statements.TransactionScope> Для получения дополнительной информации <xref:System.Transactions.Transaction?displayProperty=nameWithType>о транзакциях, см. <xref:System.Transactions?displayProperty=nameWithType>  
  
## <a name="using-compensableactivity"></a>Использование действия CompensableActivity  
 <xref:System.Activities.Statements.CompensableActivity> - это базовое действие компенсации в [!INCLUDE[wf1](../../../includes/wf1-md.md)]. Все выполняющие работу действия, для которых может понадобиться выполнить компенсацию, помещаются в элемент <xref:System.Activities.Statements.CompensableActivity.Body%2A> действия <xref:System.Activities.Statements.CompensableActivity>. В данном примере шаг бронирования при покупке авиабилета размещен в элементе <xref:System.Activities.Statements.CompensableActivity.Body%2A> действия <xref:System.Activities.Statements.CompensableActivity>, а отмена бронирования помещается в обработчик <xref:System.Activities.Statements.CompensableActivity.CompensationHandler%2A>. Сразу за действием <xref:System.Activities.Statements.CompensableActivity> в рабочем процессе идут два действия, ожидающие одобрения от диспетчера и выполняющие шаг приобретения билета. Если состояние ошибки вызывает отмену рабочего процесса после успешного завершения работы действия <xref:System.Activities.Statements.CompensableActivity>, то действия в обработчике <xref:System.Activities.Statements.CompensableActivity.CompensationHandler%2A> планируются к выполнению, а полет отменяется.  
  
 [!code-csharp[CFX_CompensationExample#1](~/samples/snippets/csharp/VS_Snippets_CFX/CFX_CompensationExample/cs/Program.cs#1)]  
  
 Далее показан пример рабочего процесса в XAML.  
  
```xaml  
<Sequence  
   xmlns="http://schemas.microsoft.com/netfx/2009/xaml/activities"  
   xmlns:c="clr-namespace:CompensationExample;assembly=CompensationExample"  
   xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml">  
  <CompensableActivity>  
    <CompensableActivity.Result>  
      <OutArgument  
         x:TypeArguments="CompensationToken" />  
    </CompensableActivity.Result>  
    <CompensableActivity.CompensationHandler>  
      <c:CancelFlight />  
    </CompensableActivity.CompensationHandler>  
    <c:ReserveFlight />  
  </CompensableActivity>  
  <c:ManagerApproval />  
  <c:PurchaseFlight />  
</Sequence>  
```  
  
 При вызове рабочего процесса на консоль выводятся следующие данные.  
  
 **ReserveFlight: Билет зарезервирован.**  
**ManagerApproval: Менеджер одобрение получено.** 
 **PurchaseFlight: Билет приобретается.** 
 **Рабочий процесс успешно завершен со статусом: Закрыто.**
> [!NOTE]
> В образцах действий этого раздела, таких как `ReserveFlight`, на консоли отображается их название и назначение для иллюстрации порядка, в котором действия выполняются при возникновении компенсации.  
  
### <a name="default-workflow-compensation"></a>Компенсация рабочего процесса по умолчанию  
 По умолчанию, если рабочий процесс отменяется, то логика компенсации выполняется для всех подлежащих компенсации действий, которые уже успешно выполнены, но еще не были подтверждены или компенсированы.  
  
> [!NOTE]
> При <xref:System.Activities.Statements.CompensableActivity> *подтверждении,* компенсация за действие больше не может быть вызвана. Процесс подтверждения описывается далее в этом разделе.  
  
 В данном примере исключение выдается после бронирования авиабилета, но до шага подтверждения диспетчера.  
  
 [!code-csharp[CFX_CompensationExample#2](~/samples/snippets/csharp/VS_Snippets_CFX/CFX_CompensationExample/cs/Program.cs#2)]  
  
 Этот пример является рабочим процессом в XAML.  
  
```xaml  
<Sequence  
   xmlns="http://schemas.microsoft.com/netfx/2009/xaml/activities"  
   xmlns:c="clr-namespace:CompensationExample;assembly=CompensationExample"  
   xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml">  
  <CompensableActivity>  
    <CompensableActivity.Result>  
      <OutArgument  
         x:TypeArguments="CompensationToken" />  
    </CompensableActivity.Result>  
    <CompensableActivity.CompensationHandler>  
      <c:CancelFlight />  
    </CompensableActivity.CompensationHandler>  
    <c:ReserveFlight />  
  </CompensableActivity>  
  <c:SimulatedErrorCondition />  
  <c:ManagerApproval />  
  <c:PurchaseFlight />  
</Sequence>  
```  
  
 [!code-csharp[CFX_CompensationExample#100](~/samples/snippets/csharp/VS_Snippets_CFX/CFX_CompensationExample/cs/Program.cs#100)]  
  
 Если вызывается рабочий процесс, исключение смоделированного условия ошибки обрабатывается ведущим приложением в <xref:System.Activities.WorkflowApplication.OnUnhandledException%2A>, рабочий процесс отменяется, и вызывается логика компенсации.  
  
 **ReserveFlight: Билет зарезервирован.**  
**ИмитированноеОшибкаОшибка: Бросок приложенияИсключение.** 
 **Необработанное исключение рабочего процесса:**
**System.ApplicationException: Смоделированное условие ошибки в рабочем процессе.** 
 **Отмена рейса: Билет отменяется.** 
 **Рабочий процесс успешно завершен со статусом: Отменен.**
### <a name="cancellation-and-compensableactivity"></a>Отмена и CompensableActivity  
 Если действия в теле <xref:System.Activities.Statements.CompensableActivity.Body%2A> объекта <xref:System.Activities.Statements.CompensableActivity> не завершены, и действие отменено, выполняются действия в обработчике <xref:System.Activities.Statements.CompensableActivity.CancellationHandler%2A>.  
  
> [!NOTE]
> Обработчик <xref:System.Activities.Statements.CompensableActivity.CancellationHandler%2A> вызывается, только если действия в теле <xref:System.Activities.Statements.CompensableActivity.Body%2A> объекта <xref:System.Activities.Statements.CompensableActivity> не завершены, и действие отменено. Обработчик <xref:System.Activities.Statements.CompensableActivity.CompensationHandler%2A> выполняется, только если действия в теле <xref:System.Activities.Statements.CompensableActivity.Body%2A> объекта <xref:System.Activities.Statements.CompensableActivity> успешно завершены, после чего на действии вызвана компенсация.  
  
 Обработчик <xref:System.Activities.Statements.CompensableActivity.CancellationHandler%2A> предоставляет разработчикам рабочего процесса возможность предоставить соответствующую логику отмены. В следующем примере во время выполнения <xref:System.Activities.Statements.CompensableActivity.Body%2A> создается исключение, а затем вызывается обработчик <xref:System.Activities.Statements.CompensableActivity.CancellationHandler%2A>.  
  
```csharp  
Activity wf = new Sequence()  
{  
    Activities =  
    {  
        new CompensableActivity  
        {  
            Body = new Sequence  
            {  
                Activities =
                {  
                    new ChargeCreditCard(),  
                    new SimulatedErrorCondition(),  
                    new ReserveFlight()  
                }  
            },  
            CompensationHandler = new CancelFlight(),  
            CancellationHandler = new CancelCreditCard()  
        },  
        new ManagerApproval(),  
        new PurchaseFlight()  
    }  
};  
```  
  
 Этот пример является рабочим процессом в XAML.  
  
```xaml  
<Sequence  
   xmlns="http://schemas.microsoft.com/netfx/2009/xaml/activities"  
   xmlns:c="clr-namespace:CompensationExample;assembly=CompensationExample"  
   xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml">  
  <CompensableActivity>  
    <CompensableActivity.Result>  
      <OutArgument  
         x:TypeArguments="CompensationToken" />  
    </CompensableActivity.Result>  
    <Sequence>  
      <c:ChargeCreditCard />  
      <c:SimulatedErrorCondition />  
      <c:ReserveFlight />  
    </Sequence>  
    <CompensableActivity.CancellationHandler>  
      <c:CancelCreditCard />  
    </CompensableActivity.CancellationHandler>  
    <CompensableActivity.CompensationHandler>  
      <c:CancelFlight />  
    </CompensableActivity.CompensationHandler>  
  </CompensableActivity>  
  <c:ManagerApproval />  
  <c:PurchaseFlight />  
</Sequence>  
```  
  
 Если вызывается рабочий процесс, исключение смоделированного условия ошибки обрабатывается ведущим приложением в <xref:System.Activities.WorkflowApplication.OnUnhandledException%2A>, рабочий процесс отменяется, и вызывается логика отмены объекта <xref:System.Activities.Statements.CompensableActivity>. В этом примере логика компенсации и логика отмены имеют различные задачи. Успешное завершение <xref:System.Activities.Statements.CompensableActivity.Body%2A> означает, что с кредитной карты были списаны средства, а авиабилет заказан, поэтому компенсация должна отменить оба шага. (В этом примере отмена рейса автоматически отменяет платежи по кредитной карте.) Однако, <xref:System.Activities.Statements.CompensableActivity> если отменен, это <xref:System.Activities.Statements.CompensableActivity.Body%2A> означает, что не завершена, и поэтому логика <xref:System.Activities.Statements.CompensableActivity.CancellationHandler%2A> потребностей, чтобы быть в состоянии определить, как наилучшим образом справиться с отменой. В этом примере <xref:System.Activities.Statements.CompensableActivity.CancellationHandler%2A> отменяет начисление обязательства на кредитную карту, но, поскольку `ReserveFlight` было последним действием в <xref:System.Activities.Statements.CompensableActivity.Body%2A>, попытка отмены авиабилета не выполняется. Поскольку `ReserveFlight` было последним действием в <xref:System.Activities.Statements.CompensableActivity.Body%2A>, если оно успешно завершилось, то <xref:System.Activities.Statements.CompensableActivity.Body%2A> также завершилась и отмена невозможна.  
  
 **ChargeCreditCard: начисление обязательства на кредитную карту за авиабилет.**  
**ИмитированноеОшибкаОшибка: Бросок приложенияИсключение.** 
 **Необработанное исключение рабочего процесса:**
**System.ApplicationException: Смоделированное условие ошибки в рабочем процессе.** 
 **CancelCreditCard: Отмена платежей по кредитной карте.** 
 **Рабочий процесс успешно завершен со статусом: Отменен.**  Для получения дополнительной информации об отмене [см.](modeling-cancellation-behavior-in-workflows.md)  
  
### <a name="explicit-compensation-using-the-compensate-activity"></a>Явная компенсация с использованием действия компенсации  
 В предыдущем разделе была описана неявная компенсация. Неявная компенсация может использоваться в простых сценариях, но если требуется более явный контроль над планированием обработки компенсации, можно использовать действие <xref:System.Activities.Statements.Compensate>. Для инициации процесса компенсации с применением действия <xref:System.Activities.Statements.Compensate> используется маркер <xref:System.Activities.Statements.CompensationToken> действия <xref:System.Activities.Statements.CompensableActivity>, для которого необходимо провести компенсацию. Действие <xref:System.Activities.Statements.Compensate> может использоваться для запуска компенсации для любого выполненного действия <xref:System.Activities.Statements.CompensableActivity>, которое не было подтверждено или компенсировано. Например, действие <xref:System.Activities.Statements.Compensate> может использоваться в разделе <xref:System.Activities.Statements.TryCatch.Catches%2A> действия <xref:System.Activities.Statements.TryCatch> или в любой момент после завершения действия <xref:System.Activities.Statements.CompensableActivity>. В данном примере действие <xref:System.Activities.Statements.Compensate> используется в разделе <xref:System.Activities.Statements.TryCatch.Catches%2A> действия <xref:System.Activities.Statements.TryCatch> для обращения действия <xref:System.Activities.Statements.CompensableActivity>.  
  
 [!code-csharp[CFX_CompensationExample#3](~/samples/snippets/csharp/VS_Snippets_CFX/CFX_CompensationExample/cs/Program.cs#3)]  
  
 Этот пример является рабочим процессом в XAML.  
  
```xaml  
<TryCatch  
   xmlns="http://schemas.microsoft.com/netfx/2009/xaml/activities"  
   xmlns:c="clr-namespace:CompensationExample;assembly=CompensationExample"  
   xmlns:s="clr-namespace:System;assembly=mscorlib"  
   xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml">  
  <TryCatch.Variables>  
    <Variable  
       x:TypeArguments="CompensationToken"  
       x:Name="__ReferenceID0"  
       Name="token1" />  
  </TryCatch.Variables>  
  <TryCatch.Try>  
    <Sequence>  
      <CompensableActivity>  
        <CompensableActivity.Result>  
          <OutArgument  
             x:TypeArguments="CompensationToken">  
            <VariableReference  
               x:TypeArguments="CompensationToken"  
               Variable="{x:Reference __ReferenceID0}">  
              <VariableReference.Result>  
                <OutArgument  
                   x:TypeArguments="Location(CompensationToken)" />  
              </VariableReference.Result>  
            </VariableReference>  
          </OutArgument>  
        </CompensableActivity.Result>  
        <CompensableActivity.CompensationHandler>  
          <c:CancelFlight />  
        </CompensableActivity.CompensationHandler>  
        <CompensableActivity.ConfirmationHandler>  
          <c:ConfirmFlight />  
        </CompensableActivity.ConfirmationHandler>  
        <c:ReserveFlight />  
      </CompensableActivity>  
      <c:SimulatedErrorCondition />  
      <c:ManagerApproval />  
      <c:PurchaseFlight />  
    </Sequence>  
  </TryCatch.Try>  
  <TryCatch.Catches>  
    <Catch  
       x:TypeArguments="s:ApplicationException">  
      <ActivityAction  
         x:TypeArguments="s:ApplicationException">  
        <Compensate>  
          <Compensate.Target>  
            <InArgument  
               x:TypeArguments="CompensationToken">  
              <VariableValue  
                 x:TypeArguments="CompensationToken"  
                 Variable="{x:Reference __ReferenceID0}">  
                <VariableValue.Result>  
                  <OutArgument  
                     x:TypeArguments="CompensationToken" />  
                </VariableValue.Result>  
              </VariableValue>  
            </InArgument>  
          </Compensate.Target>  
        </Compensate>  
      </ActivityAction>  
    </Catch>  
  </TryCatch.Catches>  
</TryCatch>  
```  
  
 При вызове рабочего процесса на консоль выводятся следующие данные.  
  
 **ReserveFlight: Билет зарезервирован.**  
**ИмитированноеОшибкаОшибка: Бросок приложенияИсключение.** 
 **Отмена рейса: Билет отменяется.** 
 **Рабочий процесс успешно завершен со статусом: Закрыто.**
### <a name="confirming-compensation"></a>Подтверждение компенсации  
 По умолчанию подлежащие компенсации действия могут быть компенсированы в любой момент после их завершения. Но в некоторых ситуациях это может быть невозможно. В предыдущем примере компенсацией для бронирования авиабилета служит отмена бронирования. Однако после выполнения перелета такой шаг компенсации уже недопустим. Подтверждение подлежащего компенсации действия вызывает действие, заданное обработчиком <xref:System.Activities.Statements.CompensableActivity.ConfirmationHandler%2A>. Это может использоваться, например, для освобождения любых ресурсов, которые требуются при выполнении компенсации. После подтверждения действия, которое могло быть компенсировано, его компенсация становится невозможной, и при попытке такой компенсации возникнет исключение <xref:System.InvalidOperationException>. Если рабочий процесс завершается успешно, все неподтвержденные и некомпенсированные действия, завершенные успешно, подтверждаются в порядке, обратном порядку их завершения. В данном примере авиабилет бронируется, приобретается и завершается, после чего выполняется подтверждение действия, подлежащего компенсации. Для подтверждения действия <xref:System.Activities.Statements.CompensableActivity> следует использовать действие <xref:System.Activities.Statements.Confirm> и задать маркер <xref:System.Activities.Statements.CompensationToken> действия <xref:System.Activities.Statements.CompensableActivity>, подлежащего подтверждению.  
  
 [!code-csharp[CFX_CompensationExample#4](~/samples/snippets/csharp/VS_Snippets_CFX/CFX_CompensationExample/cs/Program.cs#4)]  
  
 Этот пример является рабочим процессом в XAML.  
  
```xaml  
<Sequence  
   xmlns="http://schemas.microsoft.com/netfx/2009/xaml/activities"  
   xmlns:c="clr-namespace:CompensationExample;assembly=CompensationExample"  
   xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml">  
  <Sequence.Variables>  
    <x:Reference>__ReferenceID0</x:Reference>  
  </Sequence.Variables>  
  <CompensableActivity>  
    <CompensableActivity.Result>  
      <OutArgument  
         x:TypeArguments="CompensationToken">  
        <VariableReference  
           x:TypeArguments="CompensationToken">  
          <VariableReference.Result>  
            <OutArgument  
               x:TypeArguments="Location(CompensationToken)" />  
          </VariableReference.Result>  
          <VariableReference.Variable>  
            <Variable  
               x:TypeArguments="CompensationToken"  
               x:Name="__ReferenceID0"  
               Name="token1" />  
          </VariableReference.Variable>  
        </VariableReference>  
      </OutArgument>  
    </CompensableActivity.Result>  
    <CompensableActivity.CompensationHandler>  
      <c:CancelFlight />  
    </CompensableActivity.CompensationHandler>  
    <CompensableActivity.ConfirmationHandler>  
      <c:ConfirmFlight />  
    </CompensableActivity.ConfirmationHandler>  
    <c:ReserveFlight />  
  </CompensableActivity>  
  <c:ManagerApproval />  
  <c:PurchaseFlight />  
  <c:TakeFlight />  
  <Confirm>  
    <Confirm.Target>  
      <InArgument  
         x:TypeArguments="CompensationToken">  
        <VariableValue  
           x:TypeArguments="CompensationToken"  
           Variable="{x:Reference __ReferenceID0}">  
          <VariableValue.Result>  
            <OutArgument  
               x:TypeArguments="CompensationToken" />  
          </VariableValue.Result>  
        </VariableValue>  
      </InArgument>  
    </Confirm.Target>  
  </Confirm>  
</Sequence>  
```  
  
При вызове рабочего процесса на консоль выводятся следующие данные.  
  
**ReserveFlight: Билет зарезервирован.**  
**ManagerApproval: Менеджер одобрение получено.** 
 **PurchaseFlight: Билет приобретается.** 
 **TakeFlight: Полет завершен.** 
 **ConfirmFlight: Полет был взят, компенсация невозможна.** 
 **Рабочий процесс успешно завершен со статусом: Закрыто.**

## <a name="nesting-compensation-activities"></a>Вложенные действия компенсации  

Действие <xref:System.Activities.Statements.CompensableActivity> может быть помещено в раздел <xref:System.Activities.Statements.CompensableActivity.Body%2A> другого действия <xref:System.Activities.Statements.CompensableActivity>. Объект <xref:System.Activities.Statements.CompensableActivity> не может быть помещен в обработчик другого <xref:System.Activities.Statements.CompensableActivity>. Родительское действие <xref:System.Activities.Statements.CompensableActivity> обязано убедиться в том, что при отмене, подтверждении или компенсации все дочерние действия, подлежащие компенсации, которые успешно завершились и еще не подтверждены и не компенсированы, должны быть подтверждены или компенсированы перед тем, как родительское действие завершит отмену, подтверждение или компенсацию. Если это не моделируется явным образом, родительское действие <xref:System.Activities.Statements.CompensableActivity> неявно компенсирует дочерние действия, подлежащие компенсации, если получит сигнал отмены или компенсации. Если родитель получил сигнал подтверждения, родитель неявно подтвердит дочерние действия, подлежащие компенсации. Если логика обработки отмены, подтверждения или компенсации явным образом моделируется в обработчике родительского <xref:System.Activities.Statements.CompensableActivity>, то любое явно не обработанное дочернее действие будет неявно подтверждено.  
  
## <a name="see-also"></a>См. также раздел

- <xref:System.Activities.Statements.CompensableActivity>
- <xref:System.Activities.Statements.Compensate>
- <xref:System.Activities.Statements.Confirm>
- <xref:System.Activities.Statements.CompensationToken>
