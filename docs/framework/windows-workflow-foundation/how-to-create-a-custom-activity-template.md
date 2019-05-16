---
title: Практическое руководство. Создание настраиваемого шаблона действий
ms.date: 03/30/2017
ms.assetid: 6760a5cc-6eb8-465f-b4fa-f89b39539429
ms.openlocfilehash: f54a625fbe5497406645ea29f824d361c0392eb3
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/15/2019
ms.locfileid: "65637728"
---
# <a name="how-to-create-a-custom-activity-template"></a><span data-ttu-id="e6201-102">Практическое руководство. Создание настраиваемого шаблона действий</span><span class="sxs-lookup"><span data-stu-id="e6201-102">How to: Create a Custom Activity Template</span></span>

<span data-ttu-id="e6201-103">Настраиваемые шаблоны действий служат для настройки конфигурации действий, в том числе настраиваемых составных действий, чтобы позволяет не создавать отдельно каждое действие и не настраивать все свойства и другие параметры вручную.</span><span class="sxs-lookup"><span data-stu-id="e6201-103">Custom activity templates are used to customize the configuration of activities, including custom composite activities, so that users do not have to create each activity individually and configure their properties and other settings manually.</span></span> <span data-ttu-id="e6201-104">Эти настраиваемые шаблоны могут быть сделаны доступными в **элементов** на [!INCLUDE[wfd1](../../../includes/wfd1-md.md)] или в повторно размещенном конструкторе, из которого пользователи могут перетащить их в предварительно настроенную область конструктора.</span><span class="sxs-lookup"><span data-stu-id="e6201-104">These custom templates can be made available in the **Toolbox** on the [!INCLUDE[wfd1](../../../includes/wfd1-md.md)] or from a rehosted designer, from which users can drag them onto the preconfigured design surface.</span></span> [!INCLUDE[wfd2](../../../includes/wfd2-md.md)] <span data-ttu-id="e6201-105">поставляется с хорошими примерами таких шаблонов: [конструктора шаблонов SendAndReceiveReply](/visualstudio/workflow-designer/sendandreceivereply-template-designer) и [конструктора шаблонов ReceiveAndSendReply](/visualstudio/workflow-designer/receiveandsendreply-template-designer) в [конструкторы действий обмена сообщениями](/visualstudio/workflow-designer/messaging-activity-designers) категории.</span><span class="sxs-lookup"><span data-stu-id="e6201-105">ships with good examples of such templates: the [SendAndReceiveReply Template Designer](/visualstudio/workflow-designer/sendandreceivereply-template-designer) and the [ReceiveAndSendReply Template Designer](/visualstudio/workflow-designer/receiveandsendreply-template-designer) in the [Messaging Activity Designers](/visualstudio/workflow-designer/messaging-activity-designers) category.</span></span>

 <span data-ttu-id="e6201-106">Первая процедура в этом разделе описывается создание настраиваемого шаблона действий для **задержка** действия, а вторая процедура кратко описывает способ сделать его доступным в [!INCLUDE[wfd2](../../../includes/wfd2-md.md)] для проверки работы пользовательского шаблона.</span><span class="sxs-lookup"><span data-stu-id="e6201-106">The first procedure in this topic describes how to create a custom activity template for a **Delay** activity and the second procedure describes briefly how to make it available in a [!INCLUDE[wfd2](../../../includes/wfd2-md.md)] to verify that the custom template works.</span></span>

 <span data-ttu-id="e6201-107">В шаблонах настраиваемых действий должен быть реализован интерфейс <xref:System.Activities.Presentation.IActivityTemplateFactory>.</span><span class="sxs-lookup"><span data-stu-id="e6201-107">Custom activity templates must implement the <xref:System.Activities.Presentation.IActivityTemplateFactory>.</span></span> <span data-ttu-id="e6201-108">Интерфейс имеет один метод <xref:System.Activities.Presentation.IActivityTemplateFactory.Create%2A>, с помощью которого можно создать и настроить экземпляры действий, используемые в шаблоны.</span><span class="sxs-lookup"><span data-stu-id="e6201-108">The interface has a single <xref:System.Activities.Presentation.IActivityTemplateFactory.Create%2A> method with which you can create and configure the activity instances used in the template.</span></span>

## <a name="to-create-a-template-for-the-delay-activity"></a><span data-ttu-id="e6201-109">Создание шаблона для действия Delay</span><span class="sxs-lookup"><span data-stu-id="e6201-109">To create a template for the Delay activity</span></span>

1. <span data-ttu-id="e6201-110">Запустите Visual Studio 2010.</span><span class="sxs-lookup"><span data-stu-id="e6201-110">Start Visual Studio 2010.</span></span>

2. <span data-ttu-id="e6201-111">В меню **Файл** наведите указатель мыши на элемент **Создать** и выберите **Проект**.</span><span class="sxs-lookup"><span data-stu-id="e6201-111">On the **File** menu, point to **New**, and then select **Project**.</span></span>

     <span data-ttu-id="e6201-112">Откроется диалоговое окно **Новый проект** .</span><span class="sxs-lookup"><span data-stu-id="e6201-112">The **New Project** dialog box opens.</span></span>

3. <span data-ttu-id="e6201-113">В **типы проектов** области выберите **рабочего процесса** либо из **Visual C#** проектов или **Visual Basic** группирований, в зависимости от вашей предпочитаемый язык.</span><span class="sxs-lookup"><span data-stu-id="e6201-113">In the **Project Types** pane, select **Workflow** from either the **Visual C#** projects or **Visual Basic** groupings depending on your language preference.</span></span>

4. <span data-ttu-id="e6201-114">В **шаблоны** области выберите **библиотеки действий**.</span><span class="sxs-lookup"><span data-stu-id="e6201-114">In the **Templates** pane, select **Activity Library**.</span></span>

5. <span data-ttu-id="e6201-115">В **имя** введите `DelayActivityTemplate`.</span><span class="sxs-lookup"><span data-stu-id="e6201-115">In the **Name** box, enter `DelayActivityTemplate`.</span></span>

6. <span data-ttu-id="e6201-116">Примите значения по умолчанию в **расположение** и **имя решения** текстовые поля и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="e6201-116">Accept the defaults in the **Location** and **Solution name** text boxes, and then click **OK**.</span></span>

7. <span data-ttu-id="e6201-117">Щелкните правой кнопкой мыши каталог References проекта DelayActivityTemplate в **обозревателе решений** и выберите **добавить ссылку** открыть **добавить ссылку** диалоговое окно.</span><span class="sxs-lookup"><span data-stu-id="e6201-117">Right-click the References directory of the DelayActivityTemplate project in **Solution Explorer** and choose **Add Reference** to open the **Add Reference** dialog box.</span></span>

8. <span data-ttu-id="e6201-118">Перейдите к **.NET** и выберите **PresentationFramework** из **имя компонента** столбец слева и выберите **ОК** для добавления ссылки на файл PresentationFramework.dll.</span><span class="sxs-lookup"><span data-stu-id="e6201-118">Go to the **.NET** tab and select **PresentationFramework** from the **Component Name** column on the left and click **OK** to add a reference to the PresentationFramework.dll file.</span></span>

9. <span data-ttu-id="e6201-119">Повторите процедуру для добавления ссылок на файлы System.Activities.Presentation.dll and the WindowsBase.dll.</span><span class="sxs-lookup"><span data-stu-id="e6201-119">Repeat this procedure to add references to the System.Activities.Presentation.dll and the WindowsBase.dll files.</span></span>

10. <span data-ttu-id="e6201-120">Щелкните правой кнопкой мыши проект в окне **обозревателе решений** и выберите **добавить** и затем **новый элемент** открыть **Добавление нового элемента**диалоговое окно.</span><span class="sxs-lookup"><span data-stu-id="e6201-120">Right-click the DelayActivityTemplate project in **Solution Explorer** and choose **Add** and then **New Item** to open the **Add New Item** dialog box.</span></span>

11. <span data-ttu-id="e6201-121">Выберите **класс** шаблона, назовите его MyDelayTemplate, затем нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="e6201-121">Select the **Class** template, name it MyDelayTemplate, and then click **OK**.</span></span>

12. <span data-ttu-id="e6201-122">Откройте файл MyDelayTemplate.cs и добавьте следующие инструкции.</span><span class="sxs-lookup"><span data-stu-id="e6201-122">Open the MyDelayTemplate.cs file and add the following statements.</span></span>

    ```
    //Namespaces added
    using System.Activities;
    using System.Activities.Statements;
    using System.Activities.Presentation;
    using System.Windows;
    ```

13. <span data-ttu-id="e6201-123">Реализуйте метод <xref:System.Activities.Presentation.IActivityTemplateFactory> с помощью класса `MyDelayActivity` со следующим кодом.</span><span class="sxs-lookup"><span data-stu-id="e6201-123">Implement the <xref:System.Activities.Presentation.IActivityTemplateFactory> with the `MyDelayActivity` class with the following code.</span></span> <span data-ttu-id="e6201-124">Это настраивает задержку на длительность 10 секунд.</span><span class="sxs-lookup"><span data-stu-id="e6201-124">This configures the delay to have a duration of 10 seconds.</span></span>

    ```
    public sealed class MyDelayActivity : IActivityTemplateFactory
    {
        public Activity Create(System.Windows.DependencyObject target)
        {
            return new System.Activities.Statements.Delay
            {
                DisplayName = "DelayActivityTemplate",
                Duration = new TimeSpan(0, 0, 10)

            };
        }
    }
    ```

14. <span data-ttu-id="e6201-125">Выберите **построить решение** из **построения** меню, чтобы создать файл DelayActivityTemplate.dll.</span><span class="sxs-lookup"><span data-stu-id="e6201-125">Select **Build Solution** from the **Build** menu to generate the DelayActivityTemplate.dll file.</span></span>

### <a name="to-make-the-template-available-in-a-workflow-designer"></a><span data-ttu-id="e6201-126">Обеспечение доступности шаблона в конструкторе рабочего процесса</span><span class="sxs-lookup"><span data-stu-id="e6201-126">To make the template available in a Workflow Designer</span></span>

1. <span data-ttu-id="e6201-127">Щелкните правой кнопкой мыши решение DelayActivityTemplate в **обозревателе решений** и выберите **добавить** и затем **новый проект** открыть **Добавление нового проекта** диалоговое окно.</span><span class="sxs-lookup"><span data-stu-id="e6201-127">Right-click the DelayActivityTemplate solution in **Solution Explorer** and choose **Add** and then **New Project** to open the **Add New Project** dialog box.</span></span>

2. <span data-ttu-id="e6201-128">Выберите **консольное приложение рабочего процесса** шаблона, назовите его `CustomActivityTemplateApp`, а затем нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="e6201-128">Select the **Workflow Console Application** template, name it `CustomActivityTemplateApp`, and then click **OK**.</span></span>

3. <span data-ttu-id="e6201-129">Щелкните правой кнопкой мыши каталог References проекта CustomActivityTemplateApp в **обозревателе решений** и выберите **добавить ссылку** открыть **добавить ссылку** диалоговое окно поле.</span><span class="sxs-lookup"><span data-stu-id="e6201-129">Right-click the References directory of the CustomActivityTemplateApp project in **Solution Explorer** and choose **Add Reference** to open the **Add Reference** dialog box.</span></span>

4. <span data-ttu-id="e6201-130">Перейдите к **проекты** и выберите **DelayActivityTemplate** из **имя_проекта** столбец слева и выберите **ОК** для добавления ссылка на файл DelayActivityTemplate.dll, созданный в первой процедуре.</span><span class="sxs-lookup"><span data-stu-id="e6201-130">Go to the **Projects** tab and select **DelayActivityTemplate** from the **Project Name** column on the left and click **OK** to add a reference to the DelayActivityTemplate.dll file that you created in the first procedure.</span></span>

5. <span data-ttu-id="e6201-131">Щелкните правой кнопкой мыши проект CustomActivityTemplateApp в **обозревателе решений** и выберите **построения** для компиляции приложения.</span><span class="sxs-lookup"><span data-stu-id="e6201-131">Right-click the CustomActivityTemplateApp project in **Solution Explorer** and choose **Build** to compile the application.</span></span>

6. <span data-ttu-id="e6201-132">Щелкните правой кнопкой мыши проект CustomActivityTemplateApp в **обозревателе решений** и выберите **Назначить запускаемым проектом**.</span><span class="sxs-lookup"><span data-stu-id="e6201-132">Right-click the CustomActivityTemplateApp project in **Solution Explorer** and choose **Set as Startup Project**.</span></span>

7. <span data-ttu-id="e6201-133">Выберите **Запуск без отладки** из **Отладка** меню и нажмите любую клавишу для продолжения при появлении запроса в окне cmd.exe.</span><span class="sxs-lookup"><span data-stu-id="e6201-133">Select **Start Without Debugging** from the **Debug** menu and press any key to continue when prompted from the cmd.exe window.</span></span>

8. <span data-ttu-id="e6201-134">Откройте файл Workflow1.xaml и откройте **элементов**.</span><span class="sxs-lookup"><span data-stu-id="e6201-134">Open the Workflow1.xaml file and open the **Toolbox**.</span></span>

9. <span data-ttu-id="e6201-135">Найдите **MyDelayActivity** шаблона в **DelayActivityTemplate** категории.</span><span class="sxs-lookup"><span data-stu-id="e6201-135">Locate the **MyDelayActivity** template in the **DelayActivityTemplate** category.</span></span> <span data-ttu-id="e6201-136">Перетащите его в область конструктора.</span><span class="sxs-lookup"><span data-stu-id="e6201-136">Drag it onto the design surface.</span></span> <span data-ttu-id="e6201-137">Убедитесь в **свойства** окна, `Duration` свойство значение 10 секунд.</span><span class="sxs-lookup"><span data-stu-id="e6201-137">Confirm in the **Properties** window that the `Duration` property has been set to 10 seconds.</span></span>

## <a name="example"></a><span data-ttu-id="e6201-138">Пример</span><span class="sxs-lookup"><span data-stu-id="e6201-138">Example</span></span>
 <span data-ttu-id="e6201-139">Теперь файл MyDelayActivity.cs должен содержать следующий код.</span><span class="sxs-lookup"><span data-stu-id="e6201-139">The MyDelayActivity.cs file should contain the following code.</span></span>

```
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;

//Namespaces added
using System.Activities;
using System.Activities.Statements;
using System.Activities.Presentation;
using System.Windows;

namespace DelayActivityTemplate
{
    public sealed class MyDelayActivity : IActivityTemplateFactory
    {
        public Activity Create(System.Windows.DependencyObject target)
        {
            return new System.Activities.Statements.Delay
            {
                DisplayName = "DelayActivityTemplate",
                Duration = new TimeSpan(0, 0, 10)

            };
        }
    }
}
```

## <a name="see-also"></a><span data-ttu-id="e6201-140">См. также</span><span class="sxs-lookup"><span data-stu-id="e6201-140">See also</span></span>

- <xref:System.Activities.Presentation.IActivityTemplateFactory>
- [<span data-ttu-id="e6201-141">Настройка конструктора рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="e6201-141">Customizing the Workflow Design Experience</span></span>](customizing-the-workflow-design-experience.md)
