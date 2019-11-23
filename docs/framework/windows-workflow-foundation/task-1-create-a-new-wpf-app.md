---
title: Задача 1. Создание нового приложения Windows Presentation Foundation
ms.date: 03/30/2017
ms.assetid: 270eaeba-9492-4532-af9f-403ce5c9935b
ms.openlocfilehash: 3205840da575041b449eb841fc8084e89937fca7
ms.sourcegitcommit: 10db6551ea3c971470cf5d2cc21ba1cbcefe5c55
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/08/2019
ms.locfileid: "72031898"
---
# <a name="task-1-create-a-new-windows-presentation-foundation-application"></a><span data-ttu-id="7d449-102">Задача 1. Создание нового приложения Windows Presentation Foundation</span><span class="sxs-lookup"><span data-stu-id="7d449-102">Task 1: Create a New Windows Presentation Foundation Application</span></span>

<span data-ttu-id="7d449-103">В этой задаче вы создадите пустое приложение Windows Presentation Foundation (WPF) с помощью шаблона WPF Application Visual Studio и добавите ссылки на соответствующие сборки рабочего процесса [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7d449-103">In this task, you will create an empty Windows Presentation Foundation (WPF) application by using the WPF Application Visual Studio template and add references to the appropriate [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] workflow assemblies.</span></span>  
  
## <a name="to-create-the-wpf-application-project"></a><span data-ttu-id="7d449-104">Создание проекта приложения WPF</span><span class="sxs-lookup"><span data-stu-id="7d449-104">To create the WPF Application project</span></span>

1. <span data-ttu-id="7d449-105">Откройте Visual Studio и в меню **файл** наведите указатель на пункт **создать**и выберите **проект**.</span><span class="sxs-lookup"><span data-stu-id="7d449-105">Open Visual Studio and on the **File** menu, point to **New**, and then click **Project**.</span></span>

2. <span data-ttu-id="7d449-106">В диалоговом окне **Новый проект** выберите либо **визуальный C#**  элемент, либо **Visual Basic** на панели **Установленные шаблоны** в левой части окна.</span><span class="sxs-lookup"><span data-stu-id="7d449-106">In the **New Project** dialog box, select either **Visual C#** or **Visual Basic** from the **Installed Templates** pane on the left side of the box.</span></span> <span data-ttu-id="7d449-107">Если нужный язык не отображается, просмотрите раздел **другие языки**.</span><span class="sxs-lookup"><span data-stu-id="7d449-107">If the language of your choice does not appear, look under **Other Languages**.</span></span>

3. <span data-ttu-id="7d449-108">В области **Установленные шаблоны** выберите **Windows** .</span><span class="sxs-lookup"><span data-stu-id="7d449-108">Select **Windows** in the **Installed Templates** pane.</span></span>

4. <span data-ttu-id="7d449-109">В верхней области убедитесь, что в раскрывающемся списке выбрано (значение по умолчанию) **.NET Framework 4** , а затем выберите **приложение WPF**.</span><span class="sxs-lookup"><span data-stu-id="7d449-109">In the top pane, confirm that (the default value) **.NET Framework 4** has been selected in the drop-down list box, and then select **WPF Application**.</span></span>

5. <span data-ttu-id="7d449-110">В нижней части окна задайте имя проекта **хостингаппликатион** .</span><span class="sxs-lookup"><span data-stu-id="7d449-110">Set the name of the project to **HostingApplication** at the bottom of the window.</span></span>

6. <span data-ttu-id="7d449-111">Задайте для имени решения значение **рехостингседесигнер**.</span><span class="sxs-lookup"><span data-stu-id="7d449-111">Set the solution name to **RehostingTheDesigner**.</span></span>

7. <span data-ttu-id="7d449-112">Нажмите кнопку **ОК** , чтобы создать проект приложения.</span><span class="sxs-lookup"><span data-stu-id="7d449-112">Click **OK** to create the application project.</span></span> <span data-ttu-id="7d449-113">Visual Studio создает базовый пользовательский интерфейс WPF для приложения и включает соответствующие файлы XAML и кода программной части.</span><span class="sxs-lookup"><span data-stu-id="7d449-113">Visual Studio creates a basic WPF UI for your application and includes the appropriate XAML and code-behind files.</span></span>

8. <span data-ttu-id="7d449-114">Добавьте ссылки на сборки **воркфловмодел** .</span><span class="sxs-lookup"><span data-stu-id="7d449-114">Add references to **WorkflowModel** assemblies.</span></span> <span data-ttu-id="7d449-115">Для этого в **Обозреватель решений**щелкните правой кнопкой мыши проект **хостингаппликатион** и выберите команду **Добавить ссылку**.</span><span class="sxs-lookup"><span data-stu-id="7d449-115">To do this, in **Solution Explorer**, right-click the **HostingApplication** project and select **Add Reference**.</span></span>

9. <span data-ttu-id="7d449-116">В диалоговом окне **Добавление ссылки** перейдите на вкладку **.NET** , нажмите и удерживайте клавишу CTRL, выберите следующие сборки, а затем нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="7d449-116">In the **Add Reference** dialog box, click the **.NET** tab, hold down the CTRL key, select the following assemblies, and then click **OK**:</span></span>

    - <span data-ttu-id="7d449-117">System.Activities</span><span class="sxs-lookup"><span data-stu-id="7d449-117">System.Activities</span></span>
    - <span data-ttu-id="7d449-118">System.Activities.Presentation</span><span class="sxs-lookup"><span data-stu-id="7d449-118">System.Activities.Presentation</span></span>
    - <span data-ttu-id="7d449-119">System.Activities.Core.Presentation</span><span class="sxs-lookup"><span data-stu-id="7d449-119">System.Activities.Core.Presentation</span></span>

10. <span data-ttu-id="7d449-120">См. раздел [Задача 2. размещение конструктор рабочих процессов](task-2-host-the-workflow-designer.md) , чтобы узнать, как разместить холст конструктора рабочих процессов.</span><span class="sxs-lookup"><span data-stu-id="7d449-120">See [Task 2: Host the Workflow Designer](task-2-host-the-workflow-designer.md) to learn how to host the workflow designer design canvas.</span></span>

## <a name="see-also"></a><span data-ttu-id="7d449-121">См. также:</span><span class="sxs-lookup"><span data-stu-id="7d449-121">See also</span></span>

- [<span data-ttu-id="7d449-122">Отдельное размещение конструктора рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="7d449-122">Rehosting the Workflow Designer</span></span>](rehosting-the-workflow-designer.md)
- [<span data-ttu-id="7d449-123">Задача 2. Размещение конструктора рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="7d449-123">Task 2: Host the Workflow Designer</span></span>](task-2-host-the-workflow-designer.md)
