---
title: "Практическое руководство. Создание транзакционной службы"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1bd2e4ed-a557-43f9-ba98-4c70cb75c154
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 4a61c1c4aeba63baee3c5e2ba5110710ed9f45f2
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/19/2018
---
# <a name="how-to-create-a-transactional-service"></a><span data-ttu-id="c24bb-102">Практическое руководство. Создание транзакционной службы</span><span class="sxs-lookup"><span data-stu-id="c24bb-102">How to: Create a Transactional Service</span></span>
<span data-ttu-id="c24bb-103">В этом примере показаны различные аспекты создания транзакционной службы и использования инициируемых клиентом транзакций для координации операций службы.</span><span class="sxs-lookup"><span data-stu-id="c24bb-103">This sample demonstrates various aspects of creating a transactional service and the use of a client-initiated transaction to coordinate service operations.</span></span>  
  
### <a name="creating-a-transactional-service"></a><span data-ttu-id="c24bb-104">Создание транзакционной службы</span><span class="sxs-lookup"><span data-stu-id="c24bb-104">Creating a transactional service</span></span>  
  
1.  <span data-ttu-id="c24bb-105">Создайте контракт службы и аннотируйте операции с выбранным параметром из перечисления <xref:System.ServiceModel.TransactionFlowOption>, чтобы задать требования входящих транзакций.</span><span class="sxs-lookup"><span data-stu-id="c24bb-105">Create a service contract and annotate the operations with the desired setting from the <xref:System.ServiceModel.TransactionFlowOption> enumeration to specify the incoming transaction requirements.</span></span> <span data-ttu-id="c24bb-106">Обратите внимание, что в реализуемый класс службы также можно включить атрибут <xref:System.ServiceModel.TransactionFlowAttribute>.</span><span class="sxs-lookup"><span data-stu-id="c24bb-106">Note that you can also place the <xref:System.ServiceModel.TransactionFlowAttribute> on the service class being implemented.</span></span> <span data-ttu-id="c24bb-107">Это позволит одной реализации интерфейса, а не всем реализациям, использовать эти параметры.</span><span class="sxs-lookup"><span data-stu-id="c24bb-107">This allows for a single implementation of an interface to use these transaction settings, instead of every implementation.</span></span>  
  
    ```  
    [ServiceContract]  
    public interface ICalculator  
    {  
        [OperationContract]  
        // Use this to require an incoming transaction  
        [TransactionFlow(TransactionFlowOption.Mandatory)]  
        double Add(double n1, double n2);  
        [OperationContract]  
        // Use this to permit an incoming transaction  
        [TransactionFlow(TransactionFlowOption.Allowed)]  
        double Subtract(double n1, double n2);  
    }  
    ```  
  
2.  <span data-ttu-id="c24bb-108">Создайте класс реализации и воспользуйтесь атрибутом <xref:System.ServiceModel.ServiceBehaviorAttribute>, чтобы задать значения свойств <xref:System.ServiceModel.ServiceBehaviorAttribute.TransactionIsolationLevel%2A> и <xref:System.ServiceModel.ServiceBehaviorAttribute.TransactionTimeout%2A> (необязательно).</span><span class="sxs-lookup"><span data-stu-id="c24bb-108">Create an implementation class, and use the <xref:System.ServiceModel.ServiceBehaviorAttribute> to optionally specify a <xref:System.ServiceModel.ServiceBehaviorAttribute.TransactionIsolationLevel%2A> and a <xref:System.ServiceModel.ServiceBehaviorAttribute.TransactionTimeout%2A>.</span></span> <span data-ttu-id="c24bb-109">Обратите внимание, что во многих случаях можно использовать значения по умолчанию для свойств <xref:System.ServiceModel.ServiceBehaviorAttribute.TransactionTimeout%2A> (60 секунд) и <xref:System.ServiceModel.ServiceBehaviorAttribute.TransactionIsolationLevel%2A> (`Unspecified`).</span><span class="sxs-lookup"><span data-stu-id="c24bb-109">You should note that in many cases, the default <xref:System.ServiceModel.ServiceBehaviorAttribute.TransactionTimeout%2A> of 60 seconds and the default <xref:System.ServiceModel.ServiceBehaviorAttribute.TransactionIsolationLevel%2A> of `Unspecified` are appropriate.</span></span> <span data-ttu-id="c24bb-110">Для каждой операции можно с помощью атрибута <xref:System.ServiceModel.OperationBehaviorAttribute> определить, должны ли операции, расположенные внутри метода, выполняться в области действия транзакции в соответствии со значением атрибута <xref:System.ServiceModel.OperationBehaviorAttribute.TransactionScopeRequired%2A>.</span><span class="sxs-lookup"><span data-stu-id="c24bb-110">For each operation, you can use the <xref:System.ServiceModel.OperationBehaviorAttribute> attribute to specify whether work performed within the method should occur within the scope of a transaction scope according to the value of the <xref:System.ServiceModel.OperationBehaviorAttribute.TransactionScopeRequired%2A> attribute.</span></span> <span data-ttu-id="c24bb-111">В этом случае транзакция, используемая для метода `Add`, будет совпадать с обязательной входящей транзакцией, которая поступает от клиента, а транзакция, используемая для метода `Subtract`, либо совпадает со входящей транзакцией, если она поступила от клиента, либо является новой созданной явно локальной транзакцией.</span><span class="sxs-lookup"><span data-stu-id="c24bb-111">In this case, the transaction used for the `Add` method is the same as the mandatory incoming transaction that is flowed from the client, and the transaction used for the `Subtract` method is either the same as the incoming transaction if one was flowed from the client, or a new implicitly and locally created transaction.</span></span>  
  
    ```  
    [ServiceBehavior(  
        TransactionIsolationLevel = System.Transactions.IsolationLevel.Serializable,  
        TransactionTimeout = "00:00:45")]  
    public class CalculatorService : ICalculator  
    {  
        [OperationBehavior(TransactionScopeRequired = true)]  
        public double Add(double n1, double n2)  
        {  
            // Perform transactional operation  
            RecordToLog(String.Format("Adding {0} to {1}", n1, n2));  
            return n1 + n2;  
        }  
  
        [OperationBehavior(TransactionScopeRequired = true)]  
        public double Subtract(double n1, double n2)  
        {  
            // Perform transactional operation  
            RecordToLog(String.Format("Subtracting {0} from {1}", n2, n1));  
            return n1 - n2;  
        }  
  
        private static void RecordToLog(string recordText)  
        {  
            // Database operations omitted for brevity  
            // This is where the transaction provides specific benefit  
            // - changes to the database will be committed only when  
            // the transaction completes.  
        }  
    }  
    ```  
  
3.  <span data-ttu-id="c24bb-112">Настройте привязки в файле конфигурации, указав, что контекст транзакций должен передаваться, и необходимые для этого протоколы.</span><span class="sxs-lookup"><span data-stu-id="c24bb-112">Configure the bindings in the configuration file, specifying that the transaction context should be flowed, and the protocols to be used to do so.</span></span> [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)]<span data-ttu-id="c24bb-113">[Конфигурация транзакции ServiceModel](../../../../docs/framework/wcf/feature-details/servicemodel-transaction-configuration.md).</span><span class="sxs-lookup"><span data-stu-id="c24bb-113"> [ServiceModel Transaction Configuration](../../../../docs/framework/wcf/feature-details/servicemodel-transaction-configuration.md).</span></span> <span data-ttu-id="c24bb-114">В частности тип привязки задается в атрибуте `binding` элемента конечной точки.</span><span class="sxs-lookup"><span data-stu-id="c24bb-114">Specifically, the binding type is specified in the endpoint element’s `binding` attribute.</span></span> <span data-ttu-id="c24bb-115">[ \<Endpoint >](http://msdn.microsoft.com/library/13aa23b7-2f08-4add-8dbf-a99f8127c017) элемент содержит `bindingConfiguration` атрибут, ссылающийся на конфигурацию привязки с именем `transactionalOleTransactionsTcpBinding`, как показано в следующем образце конфигурации.</span><span class="sxs-lookup"><span data-stu-id="c24bb-115">The [\<endpoint>](http://msdn.microsoft.com/library/13aa23b7-2f08-4add-8dbf-a99f8127c017) element contains a `bindingConfiguration` attribute that references a binding configuration named `transactionalOleTransactionsTcpBinding`, as shown in the following sample configuration.</span></span>  
  
    ```xml  
    <service name="CalculatorService">  
      <endpoint address="net.tcp://localhost:8008/CalcService"  
        binding="netTcpBinding"  
        bindingConfiguration="transactionalOleTransactionsTcpBinding"  
        contract="ICalculator"  
        name="OleTransactions_endpoint" />  
    </service>  
    ```  
  
     <span data-ttu-id="c24bb-116">Поток транзакций настраивается на уровне конфигурации с помощью атрибута `transactionFlow`, а протокол транзакций задается с помощью атрибута `transactionProtocol`, как показано в следующей конфигурации.</span><span class="sxs-lookup"><span data-stu-id="c24bb-116">Transaction flow is enabled at the configuration level by using the `transactionFlow` attribute, and the transaction protocol is specified using the `transactionProtocol` attribute, as shown in the following configuration.</span></span>  
  
    ```xml  
    <bindings>  
      <netTcpBinding>  
        <binding name="transactionalOleTransactionsTcpBinding"  
          transactionFlow="true"  
          transactionProtocol="OleTransactions"/>  
      </netTcpBinding>  
    </bindings>  
    ```  
  
### <a name="supporting-multiple-transaction-protocols"></a><span data-ttu-id="c24bb-117">Поддержка нескольких протоколов транзакций</span><span class="sxs-lookup"><span data-stu-id="c24bb-117">Supporting multiple transaction protocols</span></span>  
  
1.  <span data-ttu-id="c24bb-118">Для достижения оптимальной производительности в сценариях, включающих клиенты и серверы, написанные с помощью [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)], следует использовать протокол OleTransactions.</span><span class="sxs-lookup"><span data-stu-id="c24bb-118">For optimal performance, you should use the OleTransactions protocol for scenarios involving a client and service written using [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)].</span></span> <span data-ttu-id="c24bb-119">Однако в сценариях, требующих взаимодействия со сторонним стеком протоколов, удобно использовать протокол WS-AtomicTransaction (WS-AT).</span><span class="sxs-lookup"><span data-stu-id="c24bb-119">However, the WS-AtomicTransaction (WS-AT) protocol is useful for scenarios when interoperability with third-party protocol stacks is required.</span></span> <span data-ttu-id="c24bb-120">Службы [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] можно настроить таким образом, чтобы они поддерживали оба протокола. Для этого необходимо задать несколько конечных точек с соответствующими привязками, как показано в следующем примере конфигурации.</span><span class="sxs-lookup"><span data-stu-id="c24bb-120">You can configure [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] services to accept both protocols by providing multiple endpoints with appropriate protocol-specific bindings, as shown in the following sample configuration.</span></span>  
  
    ```xml  
    <service name="CalculatorService">  
      <endpoint address="http://localhost:8000/CalcService"  
        binding="wsHttpBinding"  
        bindingConfiguration="transactionalWsatHttpBinding"  
        contract="ICalculator"  
        name="WSAtomicTransaction_endpoint" />  
      <endpoint address="net.tcp://localhost:8008/CalcService"  
        binding="netTcpBinding"  
        bindingConfiguration="transactionalOleTransactionsTcpBinding"  
        contract="ICalculator"  
        name="OleTransactions_endpoint" />  
    </service>  
    ```  
  
     <span data-ttu-id="c24bb-121">Протокол транзакций задается с помощью атрибута `transactionProtocol`.</span><span class="sxs-lookup"><span data-stu-id="c24bb-121">The transaction protocol is specified using the `transactionProtocol` attribute.</span></span> <span data-ttu-id="c24bb-122">Однако в предоставляемой системой привязке `wsHttpBinding` этого атрибута нет, поскольку эта привязка может использовать только протокол WS-AT.</span><span class="sxs-lookup"><span data-stu-id="c24bb-122">However, this attribute is absent from the system-provided `wsHttpBinding`, because this binding can only use the WS-AT protocol.</span></span>  
  
    ```xml  
    <bindings>  
      <wsHttpBinding>  
        <binding name="transactionalWsatHttpBinding"  
          transactionFlow="true" />  
      </wsHttpBinding>  
      <netTcpBinding>  
        <binding name="transactionalOleTransactionsTcpBinding"  
          transactionFlow="true"  
          transactionProtocol="OleTransactions"/>  
      </netTcpBinding>  
    </bindings>  
    ```  
  
### <a name="controlling-the-completion-of-a-transaction"></a><span data-ttu-id="c24bb-123">Управление завершением транзакций</span><span class="sxs-lookup"><span data-stu-id="c24bb-123">Controlling the completion of a transaction</span></span>  
  
1.  <span data-ttu-id="c24bb-124">По умолчанию операции [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] автоматически завершают транзакции, если не создаются необработанные исключения.</span><span class="sxs-lookup"><span data-stu-id="c24bb-124">By default, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] operations automatically complete transactions if no unhandled exceptions are thrown.</span></span> <span data-ttu-id="c24bb-125">Такое поведение можно изменить с помощью свойства <xref:System.ServiceModel.OperationBehaviorAttribute.TransactionAutoComplete%2A> и метода <xref:System.ServiceModel.OperationContext.SetTransactionComplete%2A>.</span><span class="sxs-lookup"><span data-stu-id="c24bb-125">You can modify this behavior by using the <xref:System.ServiceModel.OperationBehaviorAttribute.TransactionAutoComplete%2A> property and the <xref:System.ServiceModel.OperationContext.SetTransactionComplete%2A> method.</span></span> <span data-ttu-id="c24bb-126">Если операция должна произойти в той же транзакции, что и другая операция (например, операции дебета и кредита), можно отключить автоматическое завершение, задав для свойства <xref:System.ServiceModel.OperationBehaviorAttribute.TransactionAutoComplete%2A> значение `false`, как показано в приведенном ниже примере операции `Debit`.</span><span class="sxs-lookup"><span data-stu-id="c24bb-126">When an operation is required to occur within the same transaction as another operation (for example, a debit and credit operation), you can disable the autocomplete behavior by setting the <xref:System.ServiceModel.OperationBehaviorAttribute.TransactionAutoComplete%2A> property to `false` as shown in the following `Debit` operation example.</span></span> <span data-ttu-id="c24bb-127">Транзакция, используемая операцией `Debit`, остается незавершенной, пока не будет вызван метод, у которого свойство <xref:System.ServiceModel.OperationBehaviorAttribute.TransactionAutoComplete%2A> имеет значение `true`, как показано в операции `Credit1`, или пока не будет вызван метод <xref:System.ServiceModel.OperationContext.SetTransactionComplete%2A>, явным образом показывающий, что транзакция завершена, как показано в операции `Credit2`.</span><span class="sxs-lookup"><span data-stu-id="c24bb-127">The transaction the `Debit` operation uses is not completed until a method with the <xref:System.ServiceModel.OperationBehaviorAttribute.TransactionAutoComplete%2A> property set to `true` is called, as shown in the operation `Credit1`, or when the <xref:System.ServiceModel.OperationContext.SetTransactionComplete%2A> method is called to explicitly mark the transaction as complete, as shown in the operation `Credit2`.</span></span> <span data-ttu-id="c24bb-128">Обратите внимание, что две операции кредита показаны в этом примере для иллюстрации, и в реальной ситуации обычно используется одна операция кредита.</span><span class="sxs-lookup"><span data-stu-id="c24bb-128">Note that the two credit operations are shown for illustration purposes, and that a single credit operation would be more typical.</span></span>  
  
    ```  
    [ServiceBehavior]  
    public class CalculatorService : IAccount  
    {  
        [OperationBehavior(  
            TransactionScopeRequired = true, TransactionAutoComplete = false)]  
        public void Debit(double n)  
        {  
            // Perform debit operation  
  
            return;  
        }  
  
        [OperationBehavior(  
            TransactionScopeRequired = true, TransactionAutoComplete = true)]  
        public void Credit1(double n)  
        {  
            // Perform credit operation  
  
            return;  
        }  
  
        [OperationBehavior(  
            TransactionScopeRequired = true, TransactionAutoComplete = false)]  
        public void Credit2(double n)  
        {  
            // Perform alternate credit operation  
  
            OperationContext.Current.SetTransactionComplete();  
            return;  
        }  
    }  
    ```  
  
2.  <span data-ttu-id="c24bb-129">Если для согласования транзакций свойству <xref:System.ServiceModel.OperationBehaviorAttribute.TransactionAutoComplete%2A> присваивается значение `false`, необходимо использовать привязку с отслеживанием состояния.</span><span class="sxs-lookup"><span data-stu-id="c24bb-129">For the purposes of transaction correlation, setting the <xref:System.ServiceModel.OperationBehaviorAttribute.TransactionAutoComplete%2A> property to `false` requires the use of a sessionful binding.</span></span> <span data-ttu-id="c24bb-130">Это требование задается с помощью свойства `SessionMode` класса <xref:System.ServiceModel.ServiceContractAttribute>.</span><span class="sxs-lookup"><span data-stu-id="c24bb-130">This requirement is specified with the `SessionMode` property on the <xref:System.ServiceModel.ServiceContractAttribute>.</span></span>  
  
    ```  
    [ServiceContract(SessionMode = SessionMode.Required)]  
    public interface IAccount  
    {  
        [OperationContract]  
        [TransactionFlow(TransactionFlowOption.Allowed)]  
        void Debit(double n);  
        [OperationContract]  
        [TransactionFlow(TransactionFlowOption.Allowed)]  
        void Credit1(double n);  
        [OperationContract]  
        [TransactionFlow(TransactionFlowOption.Allowed)]  
        void Credit2(double n);  
    }  
    ```  
  
### <a name="controlling-the-lifetime-of-a-transactional-service-instance"></a><span data-ttu-id="c24bb-131">Управление временем существования экземпляра транзакционной службы</span><span class="sxs-lookup"><span data-stu-id="c24bb-131">Controlling the lifetime of a transactional service instance</span></span>  
  
1.  <span data-ttu-id="c24bb-132">Чтобы указать, нужно ли освобождать соответствующий экземпляр службы при завершении транзакции, в [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] используется свойство <xref:System.ServiceModel.ServiceBehaviorAttribute.ReleaseServiceInstanceOnTransactionComplete%2A>.</span><span class="sxs-lookup"><span data-stu-id="c24bb-132">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] uses the <xref:System.ServiceModel.ServiceBehaviorAttribute.ReleaseServiceInstanceOnTransactionComplete%2A> property to specify whether the underlying service instance is released when a transaction completes.</span></span> <span data-ttu-id="c24bb-133">Поскольку, если не задано иное значение, это свойство по умолчанию имеет значение `true`, в [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] реализован эффективный и предсказуемый механизм активации, срабатывающий в нужное время.</span><span class="sxs-lookup"><span data-stu-id="c24bb-133">Since this defaults to `true`, unless configured otherwise, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] exhibits an efficient and predictable "just-in-time" activation behavior.</span></span> <span data-ttu-id="c24bb-134">При вызове службы в последующей транзакции используется новый экземпляр службы, который не содержит признаков состояний предыдущих транзакций.</span><span class="sxs-lookup"><span data-stu-id="c24bb-134">Calls to a service on a subsequent transaction are assured a new service instance with no remnants of the previous transaction's state.</span></span> <span data-ttu-id="c24bb-135">Хотя такой подход зачастую бывает удобным, иногда может возникнуть необходимость сохранения состояния службы после завершения транзакции.</span><span class="sxs-lookup"><span data-stu-id="c24bb-135">While this is often useful, sometimes you may want to maintain state within the service instance beyond the transaction completion.</span></span> <span data-ttu-id="c24bb-136">Например, такая ситуация возникает, если извлечение или восстановление требуемого состояния или дескриптора требует большого объема ресурсов.</span><span class="sxs-lookup"><span data-stu-id="c24bb-136">Examples of this would be when required state or handles to resources are expensive to retrieve or reconstitute.</span></span> <span data-ttu-id="c24bb-137">В этом случае можно задать для свойства <xref:System.ServiceModel.ServiceBehaviorAttribute.ReleaseServiceInstanceOnTransactionComplete%2A> значение `false`.</span><span class="sxs-lookup"><span data-stu-id="c24bb-137">You can do this by setting the <xref:System.ServiceModel.ServiceBehaviorAttribute.ReleaseServiceInstanceOnTransactionComplete%2A> property to `false`.</span></span> <span data-ttu-id="c24bb-138">Если этот параметр задан, экземпляр и связанное состояние будут доступны в последующих вызовах.</span><span class="sxs-lookup"><span data-stu-id="c24bb-138">With that setting, the instance and any associated state will be available on subsequent calls.</span></span> <span data-ttu-id="c24bb-139">При использовании этого сценария необходимо внимательно следить за тем, как и когда происходят очистка и завершение состояний и транзакций.</span><span class="sxs-lookup"><span data-stu-id="c24bb-139">When using this, give careful consideration to when and how state and transactions will be cleared and completed.</span></span> <span data-ttu-id="c24bb-140">В следующем примере показано, как реализовать это, поддерживая экземпляр с помощью переменной `runningTotal`.</span><span class="sxs-lookup"><span data-stu-id="c24bb-140">The following sample demonstrates how to do this by maintaining the instance with the `runningTotal` variable.</span></span>  
  
    ```  
    [ServiceBehavior(TransactionIsolationLevel = [ServiceBehavior(  
        ReleaseServiceInstanceOnTransactionComplete = false)]  
    public class CalculatorService : ICalculator  
    {  
        double runningTotal = 0;  
  
        [OperationBehavior(TransactionScopeRequired = true)]  
        public double Add(double n)  
        {  
            // Perform transactional operation  
            RecordToLog(String.Format("Adding {0} to {1}", n, runningTotal));  
            runningTotal = runningTotal + n;  
            return runningTotal;  
        }  
  
        [OperationBehavior(TransactionScopeRequired = true)]  
        public double Subtract(double n)  
        {  
            // Perform transactional operation  
            RecordToLog(String.Format("Subtracting {0} from {1}", n, runningTotal));  
            runningTotal = runningTotal - n;  
            return runningTotal;  
        }  
  
        private static void RecordToLog(string recordText)  
        {  
            // Database operations omitted for brevity  
        }  
    }  
    ```  
  
    > [!NOTE]
    >  <span data-ttu-id="c24bb-141">Поскольку время существования экземпляра определяется внутри службы и управляется через свойство <xref:System.ServiceModel.ServiceBehaviorAttribute>, чтобы задать поведение экземпляра, изменять конфигурацию службы или контракт службы не требуется.</span><span class="sxs-lookup"><span data-stu-id="c24bb-141">Since the instance lifetime is a behavior that is internal to the service, and controlled through the <xref:System.ServiceModel.ServiceBehaviorAttribute> property, no modification to the service configuration or service contract is required to set the instance behavior.</span></span> <span data-ttu-id="c24bb-142">Кроме того, это не отразится на сети.</span><span class="sxs-lookup"><span data-stu-id="c24bb-142">In addition, the wire will contain no representation of this.</span></span>
