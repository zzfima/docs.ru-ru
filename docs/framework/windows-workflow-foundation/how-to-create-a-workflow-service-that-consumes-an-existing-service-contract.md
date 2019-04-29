---
title: Практическое руководство. Создание службы рабочих процессов, использующей существующий контракт службы
ms.date: 03/30/2017
ms.assetid: 11d11b59-acc4-48bf-8e4b-e97b516aa0a9
ms.openlocfilehash: c2ca9c349718c3939d74d052ff0ed448879cd045
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61945578"
---
# <a name="how-to-create-a-workflow-service-that-consumes-an-existing-service-contract"></a><span data-ttu-id="e4ac7-102">Практическое руководство. Создание службы рабочих процессов, использующей существующий контракт службы</span><span class="sxs-lookup"><span data-stu-id="e4ac7-102">How to: Create a workflow service that consumes an existing service contract</span></span>
[!INCLUDE[net_v45](../../../includes/net-v45-md.md)] <span data-ttu-id="e4ac7-103">отличается улучшенной интеграцией между веб-службами и рабочими процессами в форме разработки рабочего процесса на основе контракта.</span><span class="sxs-lookup"><span data-stu-id="e4ac7-103">features better integration between web services and workflows in the form of contract-first workflow development.</span></span> <span data-ttu-id="e4ac7-104">Средство разработки рабочих процессов на основе контракта позволяет создать контракт в Code First.</span><span class="sxs-lookup"><span data-stu-id="e4ac7-104">The contract-first workflow development tool allows you to design the contract in code first.</span></span> <span data-ttu-id="e4ac7-105">Затем это средство автоматически создает в области элементов шаблон действия для каждой операции в контракте.</span><span class="sxs-lookup"><span data-stu-id="e4ac7-105">The tool then automatically generates an activity template in the toolbox for the operations in the contract.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e4ac7-106">Этот раздел содержит пошаговые инструкции по созданию службы рабочих процессов на основе контракта.</span><span class="sxs-lookup"><span data-stu-id="e4ac7-106">This topic provides step-by-step guidance on creating a contract-first workflow service.</span></span> <span data-ttu-id="e4ac7-107">Дополнительные сведения о разработке службы рабочего процесса первого контракта, см. в разделе [разработки службы рабочего процесса первого контракта](contract-first-workflow-service-development.md).</span><span class="sxs-lookup"><span data-stu-id="e4ac7-107">For more information about contract-first workflow service development, see [Contract First Workflow Service Development](contract-first-workflow-service-development.md).</span></span>  
  
### <a name="creating-the-workflow-project"></a><span data-ttu-id="e4ac7-108">Создание проекта рабочего процесса</span><span class="sxs-lookup"><span data-stu-id="e4ac7-108">Creating the workflow project</span></span>  
  
1. <span data-ttu-id="e4ac7-109">В Visual Studio выберите **файл**, **новый проект**.</span><span class="sxs-lookup"><span data-stu-id="e4ac7-109">In Visual Studio, select **File**, **New Project**.</span></span> <span data-ttu-id="e4ac7-110">Выберите **WCF** узле **C#** узел в **шаблоны** дерева и выберите **приложение службы рабочего процесса WCF** шаблон.</span><span class="sxs-lookup"><span data-stu-id="e4ac7-110">Select the **WCF** node under the **C#** node in the **Templates** tree, and select the **WCF Workflow Service Application** template.</span></span>  
  
2. <span data-ttu-id="e4ac7-111">Назовите новый проект `ContractFirst` и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="e4ac7-111">Name the new project `ContractFirst` and click **Ok**.</span></span>  
  
### <a name="creating-the-service-contract"></a><span data-ttu-id="e4ac7-112">Создание контракта службы</span><span class="sxs-lookup"><span data-stu-id="e4ac7-112">Creating the service contract</span></span>  
  
1. <span data-ttu-id="e4ac7-113">Щелкните правой кнопкой мыши проект в **обозревателе решений** и выберите **добавить**, **новый элемент...** .</span><span class="sxs-lookup"><span data-stu-id="e4ac7-113">Right-click the project in **Solution Explorer** and select **Add**, **New Item…**.</span></span> <span data-ttu-id="e4ac7-114">Выберите **кода** узел с левой стороны экрана и **класс** шаблон в правой части.</span><span class="sxs-lookup"><span data-stu-id="e4ac7-114">Select the **Code** node on the left, and the **Class** template on the right.</span></span> <span data-ttu-id="e4ac7-115">Назовите новый класс `IBookService` и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="e4ac7-115">Name the new class `IBookService` and click **Ok**.</span></span>  
  
2. <span data-ttu-id="e4ac7-116">В верхней части появившегося окна кода добавьте в `System.Servicemodel` инструкцию Using.</span><span class="sxs-lookup"><span data-stu-id="e4ac7-116">In the top of the code window that appears, add a Using statement to `System.Servicemodel`.</span></span>  
  
    ```  
    using System.ServiceModel;  
    ```  
  
3. <span data-ttu-id="e4ac7-117">Измените образец определения класса на следующее определение интерфейса.</span><span class="sxs-lookup"><span data-stu-id="e4ac7-117">Change the sample class definition to the following interface definition.</span></span>  
  
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
  
4. <span data-ttu-id="e4ac7-118">Постройте проект, нажав клавишу **Ctrl + Shift + B**.</span><span class="sxs-lookup"><span data-stu-id="e4ac7-118">Build the project by pressing **Ctrl+Shift+B**.</span></span>  
  
### <a name="importing-the-service-contract"></a><span data-ttu-id="e4ac7-119">Импорт контракта службы</span><span class="sxs-lookup"><span data-stu-id="e4ac7-119">Importing the service contract</span></span>  
  
1. <span data-ttu-id="e4ac7-120">Щелкните правой кнопкой мыши проект в **обозревателе решений** и выберите **Импорт контракта службы**.</span><span class="sxs-lookup"><span data-stu-id="e4ac7-120">Right-click the project in **Solution Explorer** and select **Import Service Contract**.</span></span> <span data-ttu-id="e4ac7-121">В разделе  **\<текущий проект >** откройте все подузлы и выберите **IBookService**.</span><span class="sxs-lookup"><span data-stu-id="e4ac7-121">Under **\<Current Project>**, open all sub-nodes and select **IBookService**.</span></span> <span data-ttu-id="e4ac7-122">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="e4ac7-122">Click **OK**.</span></span>  
  
2. <span data-ttu-id="e4ac7-123">Откроется диалоговое окно с сообщением, что операция была завершена успешно, а созданные действия появятся в области элементов после сборки проекта.</span><span class="sxs-lookup"><span data-stu-id="e4ac7-123">A dialog will open, alerting you that the operation completed successfully, and that the generated activities will appear in the toolbox after you build the project.</span></span> <span data-ttu-id="e4ac7-124">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="e4ac7-124">Click **OK**.</span></span>  
  
3. <span data-ttu-id="e4ac7-125">Постройте проект, нажав клавишу **Ctrl + Shift + B**так, чтобы импортированные действия отобразились в области элементов.</span><span class="sxs-lookup"><span data-stu-id="e4ac7-125">Build the project by pressing **Ctrl+Shift+B**, so that the imported activities will appear in the toolbox.</span></span>  
  
4. <span data-ttu-id="e4ac7-126">В **обозревателе решений**, откройте файл Service1.xamlx.</span><span class="sxs-lookup"><span data-stu-id="e4ac7-126">In **Solution Explorer**, open Service1.xamlx.</span></span> <span data-ttu-id="e4ac7-127">Служба рабочего процесса появится в конструкторе.</span><span class="sxs-lookup"><span data-stu-id="e4ac7-127">The workflow service will appear in the designer.</span></span>  
  
5. <span data-ttu-id="e4ac7-128">Выберите **последовательности** действия.</span><span class="sxs-lookup"><span data-stu-id="e4ac7-128">Select the **Sequence** activity.</span></span> <span data-ttu-id="e4ac7-129">В окне «Свойства» щелкните **...**</span><span class="sxs-lookup"><span data-stu-id="e4ac7-129">In the Properties window, click the **…**</span></span> <span data-ttu-id="e4ac7-130">кнопки в **ImplementedContract** свойство.</span><span class="sxs-lookup"><span data-stu-id="e4ac7-130">button in the **ImplementedContract** property.</span></span> <span data-ttu-id="e4ac7-131">В **редактор коллекции типов** щелкните в появившемся окне **тип** раскрывающийся список и выберите **Выбор типов...**</span><span class="sxs-lookup"><span data-stu-id="e4ac7-131">In the **Type Collection Editor** window that appears, click the **Type** dropdown, and select the **Browse for Types…**</span></span> <span data-ttu-id="e4ac7-132">запись.</span><span class="sxs-lookup"><span data-stu-id="e4ac7-132">entry.</span></span> <span data-ttu-id="e4ac7-133">В **Обзор и Выбор типа .NET** диалогового окна в разделе  **\<текущий проект >** откройте все подузлы и выберите **IBookService**.</span><span class="sxs-lookup"><span data-stu-id="e4ac7-133">In the **Browse and Select a .NET Type** dialog, under **\<Current Project>**, open all sub-nodes and select **IBookService**.</span></span> <span data-ttu-id="e4ac7-134">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="e4ac7-134">Click **OK**.</span></span> <span data-ttu-id="e4ac7-135">В **редактор коллекции типов** диалоговое окно, нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="e4ac7-135">In the **Type Collection Editor** dialog, click **OK**.</span></span>  
  
6. <span data-ttu-id="e4ac7-136">Выберите и удалите **ReceiveRequest** и **SendResponse** действий.</span><span class="sxs-lookup"><span data-stu-id="e4ac7-136">Select and delete the **ReceiveRequest** and **SendResponse** activities.</span></span>  
  
7. <span data-ttu-id="e4ac7-137">Из панели элементов перетащите **Buy_ReceiveAndSendReply** и **Checkout_Receive** действия на **последовательная служба** действия.</span><span class="sxs-lookup"><span data-stu-id="e4ac7-137">From the toolbox, drag a **Buy_ReceiveAndSendReply** and a **Checkout_Receive** activity onto the **Sequential Service** activity.</span></span>
