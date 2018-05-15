---
title: Как создать службу рабочего процесса, которая использует существующий контракт службы
ms.date: 03/30/2017
ms.assetid: 11d11b59-acc4-48bf-8e4b-e97b516aa0a9
ms.openlocfilehash: 146b3bba3a880c780644eecd277827823793b5e8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-create-a-workflow-service-that-consumes-an-existing-service-contract"></a><span data-ttu-id="00ae9-102">Как создать службу рабочего процесса, которая использует существующий контракт службы</span><span class="sxs-lookup"><span data-stu-id="00ae9-102">How to: Create a workflow service that consumes an existing service contract</span></span>
[!INCLUDE[net_v45](../../../includes/net-v45-md.md)]<span data-ttu-id="00ae9-103"> отличается улучшенной интеграцией между веб-службами и рабочими процессами в форме разработки рабочего процесса на основе контракта.</span><span class="sxs-lookup"><span data-stu-id="00ae9-103"> features better integration between web services and workflows in the form of contract-first workflow development.</span></span> <span data-ttu-id="00ae9-104">Средство разработки рабочих процессов на основе контракта позволяет создать контракт в Code First.</span><span class="sxs-lookup"><span data-stu-id="00ae9-104">The contract-first workflow development tool allows you to design the contract in code first.</span></span> <span data-ttu-id="00ae9-105">Затем это средство автоматически создает в области элементов шаблон действия для каждой операции в контракте.</span><span class="sxs-lookup"><span data-stu-id="00ae9-105">The tool then automatically generates an activity template in the toolbox for the operations in the contract.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="00ae9-106">Этот раздел содержит пошаговые инструкции по созданию службы рабочих процессов на основе контракта.</span><span class="sxs-lookup"><span data-stu-id="00ae9-106">This topic provides step-by-step guidance on creating a contract-first workflow service.</span></span> <span data-ttu-id="00ae9-107">Дополнительные сведения о разработке решений рабочих процессов на основе контракта службы см. в разделе [контракта первого разработка служб рабочего процесса](../../../docs/framework/windows-workflow-foundation/contract-first-workflow-service-development.md).</span><span class="sxs-lookup"><span data-stu-id="00ae9-107">For more information about contract-first workflow service development, see [Contract First Workflow Service Development](../../../docs/framework/windows-workflow-foundation/contract-first-workflow-service-development.md).</span></span>  
  
### <a name="creating-the-workflow-project"></a><span data-ttu-id="00ae9-108">Создание проекта рабочего процесса</span><span class="sxs-lookup"><span data-stu-id="00ae9-108">Creating the workflow project</span></span>  
  
1.  <span data-ttu-id="00ae9-109">В Visual Studio, выберите **файл**, **новый проект**.</span><span class="sxs-lookup"><span data-stu-id="00ae9-109">In Visual Studio, select **File**, **New Project**.</span></span> <span data-ttu-id="00ae9-110">Выберите **WCF** узле **C#** узел в **шаблоны** дерева, а затем выберите **приложение службы рабочего процесса WCF** шаблона.</span><span class="sxs-lookup"><span data-stu-id="00ae9-110">Select the **WCF** node under the **C#** node in the **Templates** tree, and select the **WCF Workflow Service Application** template.</span></span>  
  
2.  <span data-ttu-id="00ae9-111">Имя для нового проекта `ContractFirst` и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="00ae9-111">Name the new project `ContractFirst` and click **Ok**.</span></span>  
  
### <a name="creating-the-service-contract"></a><span data-ttu-id="00ae9-112">Создание контракта службы</span><span class="sxs-lookup"><span data-stu-id="00ae9-112">Creating the service contract</span></span>  
  
1.  <span data-ttu-id="00ae9-113">Щелкните правой кнопкой мыши проект в **обозревателе решений** и выберите **добавить**, **новый элемент...** .</span><span class="sxs-lookup"><span data-stu-id="00ae9-113">Right-click the project in **Solution Explorer** and select **Add**, **New Item…**.</span></span> <span data-ttu-id="00ae9-114">Выберите **кода** слева, узел и **класса** справа шаблон.</span><span class="sxs-lookup"><span data-stu-id="00ae9-114">Select the **Code** node on the left, and the **Class** template on the right.</span></span> <span data-ttu-id="00ae9-115">Имя для нового класса `IBookService` и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="00ae9-115">Name the new class `IBookService` and click **Ok**.</span></span>  
  
2.  <span data-ttu-id="00ae9-116">В верхней части появившегося окна кода добавьте в `System.Servicemodel` инструкцию Using.</span><span class="sxs-lookup"><span data-stu-id="00ae9-116">In the top of the code window that appears, add a Using statement to `System.Servicemodel`.</span></span>  
  
    ```  
    using System.ServiceModel;  
    ```  
  
3.  <span data-ttu-id="00ae9-117">Измените образец определения класса на следующее определение интерфейса.</span><span class="sxs-lookup"><span data-stu-id="00ae9-117">Change the sample class definition to the following interface definition.</span></span>  
  
    ```  
    [ServiceContract]  
        public interface IBookService  
        {  
            [OperationContract]  
            void Buy(string bookName);  
  
            [OperationContract(IsOneWay=true)]  
            void Checkout();  
        }  
    ```  
  
4.  <span data-ttu-id="00ae9-118">Постройте проект, нажав клавишу **Ctrl + Shift + B**.</span><span class="sxs-lookup"><span data-stu-id="00ae9-118">Build the project by pressing **Ctrl+Shift+B**.</span></span>  
  
### <a name="importing-the-service-contract"></a><span data-ttu-id="00ae9-119">Импорт контракта службы</span><span class="sxs-lookup"><span data-stu-id="00ae9-119">Importing the service contract</span></span>  
  
1.  <span data-ttu-id="00ae9-120">Щелкните правой кнопкой мыши проект в **обозревателе решений** и выберите **Импорт контракта службы**.</span><span class="sxs-lookup"><span data-stu-id="00ae9-120">Right-click the project in **Solution Explorer** and select **Import Service Contract**.</span></span> <span data-ttu-id="00ae9-121">В разделе  **\<текущий проект >** откройте все подузлы и выберите **IBookService**.</span><span class="sxs-lookup"><span data-stu-id="00ae9-121">Under **\<Current Project>**, open all sub-nodes and select **IBookService**.</span></span> <span data-ttu-id="00ae9-122">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="00ae9-122">Click **OK**.</span></span>  
  
2.  <span data-ttu-id="00ae9-123">Откроется диалоговое окно с сообщением, что операция была завершена успешно, а созданные действия появятся в области элементов после сборки проекта.</span><span class="sxs-lookup"><span data-stu-id="00ae9-123">A dialog will open, alerting you that the operation completed successfully, and that the generated activities will appear in the toolbox after you build the project.</span></span> <span data-ttu-id="00ae9-124">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="00ae9-124">Click **OK**.</span></span>  
  
3.  <span data-ttu-id="00ae9-125">Постройте проект, нажав клавишу **Ctrl + Shift + B**таким образом, чтобы импортированные действия будет отображаться на панели инструментов.</span><span class="sxs-lookup"><span data-stu-id="00ae9-125">Build the project by pressing **Ctrl+Shift+B**, so that the imported activities will appear in the toolbox.</span></span>  
  
4.  <span data-ttu-id="00ae9-126">В **обозревателе решений**, откройте файл Service1.xamlx.</span><span class="sxs-lookup"><span data-stu-id="00ae9-126">In **Solution Explorer**, open Service1.xamlx.</span></span> <span data-ttu-id="00ae9-127">Служба рабочего процесса появится в конструкторе.</span><span class="sxs-lookup"><span data-stu-id="00ae9-127">The workflow service will appear in the designer.</span></span>  
  
5.  <span data-ttu-id="00ae9-128">Выберите **последовательности** действия.</span><span class="sxs-lookup"><span data-stu-id="00ae9-128">Select the **Sequence** activity.</span></span> <span data-ttu-id="00ae9-129">В окне «Свойства» щелкните **...**</span><span class="sxs-lookup"><span data-stu-id="00ae9-129">In the Properties window, click the **…**</span></span> <span data-ttu-id="00ae9-130">кнопки в **ImplementedContract** свойство.</span><span class="sxs-lookup"><span data-stu-id="00ae9-130">button in the **ImplementedContract** property.</span></span> <span data-ttu-id="00ae9-131">В **редактор коллекции типов** пункт в появившемся окне **тип** раскрывающийся список и выберите **поиск типов...**</span><span class="sxs-lookup"><span data-stu-id="00ae9-131">In the **Type Collection Editor** window that appears, click the **Type** dropdown, and select the **Browse for Types…**</span></span> <span data-ttu-id="00ae9-132">запись.</span><span class="sxs-lookup"><span data-stu-id="00ae9-132">entry.</span></span> <span data-ttu-id="00ae9-133">В **Обзор и Выбор типа .net тип** диалогового окна в разделе  **\<текущий проект >** откройте все подузлы и выберите **IBookService**.</span><span class="sxs-lookup"><span data-stu-id="00ae9-133">In the **Browse and Select a .Net Type** dialog, under **\<Current Project>**, open all sub-nodes and select **IBookService**.</span></span> <span data-ttu-id="00ae9-134">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="00ae9-134">Click **OK**.</span></span> <span data-ttu-id="00ae9-135">В **редактор коллекции типов** диалоговое окно, нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="00ae9-135">In the **Type Collection Editor** dialog, click **OK**.</span></span>  
  
6.  <span data-ttu-id="00ae9-136">Выберите и удалите **ReceiveRequest** и **SendResponse** действия.</span><span class="sxs-lookup"><span data-stu-id="00ae9-136">Select and delete the **ReceiveRequest** and **SendResponse** activities.</span></span>  
  
7.  <span data-ttu-id="00ae9-137">Из панели элементов перетащите **Buy_ReceiveAndSendReply** и **Checkout_Receive** действия на **последовательная служба** действия.</span><span class="sxs-lookup"><span data-stu-id="00ae9-137">From the toolbox, drag a **Buy_ReceiveAndSendReply** and a **Checkout_Receive** activity onto the **Sequential Service** activity.</span></span>
