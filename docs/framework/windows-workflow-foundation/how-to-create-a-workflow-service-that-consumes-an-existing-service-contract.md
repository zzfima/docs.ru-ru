---
title: Практическое руководство. Создание службы рабочих процессов, использующей существующий контракт службы
ms.date: 03/30/2017
ms.assetid: 11d11b59-acc4-48bf-8e4b-e97b516aa0a9
ms.openlocfilehash: 6d7fa8c9faa84efc84243387cd27aa264f6155eb
ms.sourcegitcommit: 005980b14629dfc193ff6cdc040800bc75e0a5a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/14/2019
ms.locfileid: "70989626"
---
# <a name="how-to-create-a-workflow-service-that-consumes-an-existing-service-contract"></a><span data-ttu-id="9146d-102">Практическое руководство. Создание службы рабочих процессов, использующей существующий контракт службы</span><span class="sxs-lookup"><span data-stu-id="9146d-102">How to: Create a workflow service that consumes an existing service contract</span></span>
<span data-ttu-id="9146d-103">.NET Framework 4,5 обеспечивает лучшую интеграцию между веб-службами и рабочими процессами в виде разработки рабочих процессов с помощью контрактов.</span><span class="sxs-lookup"><span data-stu-id="9146d-103">.NET Framework 4.5 features better integration between web services and workflows in the form of contract-first workflow development.</span></span> <span data-ttu-id="9146d-104">Средство разработки рабочих процессов на основе контракта позволяет создать контракт в Code First.</span><span class="sxs-lookup"><span data-stu-id="9146d-104">The contract-first workflow development tool allows you to design the contract in code first.</span></span> <span data-ttu-id="9146d-105">Затем это средство автоматически создает в области элементов шаблон действия для каждой операции в контракте.</span><span class="sxs-lookup"><span data-stu-id="9146d-105">The tool then automatically generates an activity template in the toolbox for the operations in the contract.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="9146d-106">Этот раздел содержит пошаговые инструкции по созданию службы рабочих процессов на основе контракта.</span><span class="sxs-lookup"><span data-stu-id="9146d-106">This topic provides step-by-step guidance on creating a contract-first workflow service.</span></span> <span data-ttu-id="9146d-107">Дополнительные сведения о разработке службы рабочих процессов в первую очередь см. в разделе [разработка первой службы рабочих процессов](contract-first-workflow-service-development.md)на основе контрактов.</span><span class="sxs-lookup"><span data-stu-id="9146d-107">For more information about contract-first workflow service development, see [Contract First Workflow Service Development](contract-first-workflow-service-development.md).</span></span>  
  
### <a name="creating-the-workflow-project"></a><span data-ttu-id="9146d-108">Создание проекта рабочего процесса</span><span class="sxs-lookup"><span data-stu-id="9146d-108">Creating the workflow project</span></span>  
  
1. <span data-ttu-id="9146d-109">В Visual Studio выберите **файл**, **создать проект**.</span><span class="sxs-lookup"><span data-stu-id="9146d-109">In Visual Studio, select **File**, **New Project**.</span></span> <span data-ttu-id="9146d-110">Выберите узел **WCF** в **C#** узле в дереве **шаблонов** и выберите шаблон **приложение службы рабочего процесса WCF** .</span><span class="sxs-lookup"><span data-stu-id="9146d-110">Select the **WCF** node under the **C#** node in the **Templates** tree, and select the **WCF Workflow Service Application** template.</span></span>  
  
2. <span data-ttu-id="9146d-111">Присвойте новому проекту `ContractFirst` имя и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="9146d-111">Name the new project `ContractFirst` and click **Ok**.</span></span>  
  
### <a name="creating-the-service-contract"></a><span data-ttu-id="9146d-112">Создание контракта службы</span><span class="sxs-lookup"><span data-stu-id="9146d-112">Creating the service contract</span></span>  
  
1. <span data-ttu-id="9146d-113">Щелкните правой кнопкой мыши проект в **Обозреватель решений** и выберите **Добавить**, **новый элемент...** .</span><span class="sxs-lookup"><span data-stu-id="9146d-113">Right-click the project in **Solution Explorer** and select **Add**, **New Item…**.</span></span> <span data-ttu-id="9146d-114">Выберите узел **кода** слева и шаблон **класса** справа.</span><span class="sxs-lookup"><span data-stu-id="9146d-114">Select the **Code** node on the left, and the **Class** template on the right.</span></span> <span data-ttu-id="9146d-115">Присвойте новому классу `IBookService` имя и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="9146d-115">Name the new class `IBookService` and click **Ok**.</span></span>  
  
2. <span data-ttu-id="9146d-116">В верхней части появившегося окна кода добавьте в `System.Servicemodel` инструкцию Using.</span><span class="sxs-lookup"><span data-stu-id="9146d-116">In the top of the code window that appears, add a Using statement to `System.Servicemodel`.</span></span>  
  
    ```csharp  
    using System.ServiceModel;  
    ```  
  
3. <span data-ttu-id="9146d-117">Измените образец определения класса на следующее определение интерфейса.</span><span class="sxs-lookup"><span data-stu-id="9146d-117">Change the sample class definition to the following interface definition.</span></span>  
  
    ```csharp  
    [ServiceContract]  
        public interface IBookService  
        {  
            [OperationContract]  
            void Buy(string bookName);  
  
            [OperationContract(IsOneWay=true)]  
            void Checkout();  
        }  
    ```  
  
4. <span data-ttu-id="9146d-118">Постройте проект, нажав клавиши **CTRL + SHIFT + B**.</span><span class="sxs-lookup"><span data-stu-id="9146d-118">Build the project by pressing **Ctrl+Shift+B**.</span></span>  
  
### <a name="importing-the-service-contract"></a><span data-ttu-id="9146d-119">Импорт контракта службы</span><span class="sxs-lookup"><span data-stu-id="9146d-119">Importing the service contract</span></span>  
  
1. <span data-ttu-id="9146d-120">Щелкните правой кнопкой мыши проект в **Обозреватель решений** и выберите пункт **Импорт контракта службы**.</span><span class="sxs-lookup"><span data-stu-id="9146d-120">Right-click the project in **Solution Explorer** and select **Import Service Contract**.</span></span> <span data-ttu-id="9146d-121">В разделе  **\<текущий проект >** откройте все подузлы и выберите **ибуксервице**.</span><span class="sxs-lookup"><span data-stu-id="9146d-121">Under **\<Current Project>**, open all sub-nodes and select **IBookService**.</span></span> <span data-ttu-id="9146d-122">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="9146d-122">Click **OK**.</span></span>  
  
2. <span data-ttu-id="9146d-123">Откроется диалоговое окно с сообщением, что операция была завершена успешно, а созданные действия появятся в области элементов после сборки проекта.</span><span class="sxs-lookup"><span data-stu-id="9146d-123">A dialog will open, alerting you that the operation completed successfully, and that the generated activities will appear in the toolbox after you build the project.</span></span> <span data-ttu-id="9146d-124">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="9146d-124">Click **OK**.</span></span>  
  
3. <span data-ttu-id="9146d-125">Постройте проект, нажав клавиши **CTRL + SHIFT + B**, чтобы импортированные действия отображались на панели элементов.</span><span class="sxs-lookup"><span data-stu-id="9146d-125">Build the project by pressing **Ctrl+Shift+B**, so that the imported activities will appear in the toolbox.</span></span>  
  
4. <span data-ttu-id="9146d-126">В **Обозреватель решений**откройте Service1. xamlx.</span><span class="sxs-lookup"><span data-stu-id="9146d-126">In **Solution Explorer**, open Service1.xamlx.</span></span> <span data-ttu-id="9146d-127">Служба рабочего процесса появится в конструкторе.</span><span class="sxs-lookup"><span data-stu-id="9146d-127">The workflow service will appear in the designer.</span></span>  
  
5. <span data-ttu-id="9146d-128">Выберите действие **последовательности** .</span><span class="sxs-lookup"><span data-stu-id="9146d-128">Select the **Sequence** activity.</span></span> <span data-ttu-id="9146d-129">В окно свойств щелкните **...**</span><span class="sxs-lookup"><span data-stu-id="9146d-129">In the Properties window, click the **…**</span></span> <span data-ttu-id="9146d-130">в свойстве **имплементедконтракт** .</span><span class="sxs-lookup"><span data-stu-id="9146d-130">button in the **ImplementedContract** property.</span></span> <span data-ttu-id="9146d-131">В открывшемся окне **Редактор коллекции типов** щелкните раскрывающийся список **Тип** и выберите пункт **Обзор для типов...**</span><span class="sxs-lookup"><span data-stu-id="9146d-131">In the **Type Collection Editor** window that appears, click the **Type** dropdown, and select the **Browse for Types…**</span></span> <span data-ttu-id="9146d-132">операции.</span><span class="sxs-lookup"><span data-stu-id="9146d-132">entry.</span></span> <span data-ttu-id="9146d-133">В диалоговом окне **Обзор и выбор типа .NET** в разделе  **\<текущий проект >** откройте все подузлы и выберите **ибуксервице**.</span><span class="sxs-lookup"><span data-stu-id="9146d-133">In the **Browse and Select a .NET Type** dialog, under **\<Current Project>**, open all sub-nodes and select **IBookService**.</span></span> <span data-ttu-id="9146d-134">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="9146d-134">Click **OK**.</span></span> <span data-ttu-id="9146d-135">В диалоговом окне **Редактор коллекции типов** нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="9146d-135">In the **Type Collection Editor** dialog, click **OK**.</span></span>  
  
6. <span data-ttu-id="9146d-136">Выберите и удалите действия **действия ReceiveRequest** и **SendResponse** .</span><span class="sxs-lookup"><span data-stu-id="9146d-136">Select and delete the **ReceiveRequest** and **SendResponse** activities.</span></span>  
  
7. <span data-ttu-id="9146d-137">Перетащите действие **Buy_ReceiveAndSendReply** и **Checkout_Receive** из области элементов в действие **Последовательная служба** .</span><span class="sxs-lookup"><span data-stu-id="9146d-137">From the toolbox, drag a **Buy_ReceiveAndSendReply** and a **Checkout_Receive** activity onto the **Sequential Service** activity.</span></span>
