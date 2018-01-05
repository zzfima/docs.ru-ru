---
title: "Практическое руководство. Создание элемента управления с простой привязкой в форме Windows Forms"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- data binding [Windows Forms], simple data binding
- Windows Forms controls, data binding
ms.assetid: 3bcaded8-0f1a-4cc0-8830-f59be253bf4e
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 1c55480e02eac4cc4156fa119493f2fd2f57c07a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-create-a-simple-bound-control-on-a-windows-form"></a><span data-ttu-id="46bab-102">Практическое руководство. Создание элемента управления с простой привязкой в форме Windows Forms</span><span class="sxs-lookup"><span data-stu-id="46bab-102">How to: Create a Simple-Bound Control on a Windows Form</span></span>
<span data-ttu-id="46bab-103">С *простую привязку*, одному элементу данных, например, значение столбца из таблицы набора данных, можно отобразить в элементе управления.</span><span class="sxs-lookup"><span data-stu-id="46bab-103">With *simple binding*, you can display a single data element, such as a column value from a dataset table, in a control.</span></span> <span data-ttu-id="46bab-104">Вы можете простую привязку любого свойства элемента управления к значению данных.</span><span class="sxs-lookup"><span data-stu-id="46bab-104">You can simple-bind any property of a control to a data value.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="46bab-105">Отображаемые диалоговые окна и команды меню могут отличаться от описанных в справке в зависимости от текущих параметров или выпуска.</span><span class="sxs-lookup"><span data-stu-id="46bab-105">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="46bab-106">Чтобы изменить параметры, выберите в меню **Сервис** пункт **Импорт и экспорт параметров** .</span><span class="sxs-lookup"><span data-stu-id="46bab-106">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="46bab-107">Дополнительные сведения см. в статье [Настройка параметров разработки в Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span><span class="sxs-lookup"><span data-stu-id="46bab-107">For more information, see [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span></span>  
  
### <a name="to-simple-bind-a-control"></a><span data-ttu-id="46bab-108">Чтобы выполнить простую привязку элемента управления</span><span class="sxs-lookup"><span data-stu-id="46bab-108">To simple-bind a control</span></span>  
  
1.  <span data-ttu-id="46bab-109">Подключение к источнику данных.</span><span class="sxs-lookup"><span data-stu-id="46bab-109">Connect to a data source.</span></span> <span data-ttu-id="46bab-110">Дополнительные сведения см. в разделе [соединение с источником данных](../../../docs/framework/data/adonet/connecting-to-a-data-source.md).</span><span class="sxs-lookup"><span data-stu-id="46bab-110">For more information, see [Connecting to a Data Source](../../../docs/framework/data/adonet/connecting-to-a-data-source.md).</span></span>  
  
2.  <span data-ttu-id="46bab-111">В форме выберите элемент управления и отобразить **свойства** окна.</span><span class="sxs-lookup"><span data-stu-id="46bab-111">In the form, select the control and display the **Properties** window.</span></span>  
  
3.  <span data-ttu-id="46bab-112">Разверните **(DataBindings)** свойство.</span><span class="sxs-lookup"><span data-stu-id="46bab-112">Expand the **(DataBindings)** property.</span></span>  
  
     <span data-ttu-id="46bab-113">Чаще всего привязанного свойства отображаются под **(DataBindings)** свойство.</span><span class="sxs-lookup"><span data-stu-id="46bab-113">The properties most often bound are displayed underneath the **(DataBindings)** property.</span></span> <span data-ttu-id="46bab-114">Например, для большинства элементов управления **текст** чаще всего выполняется привязка к свойству.</span><span class="sxs-lookup"><span data-stu-id="46bab-114">For example, in most controls, the **Text** property is most frequently bound.</span></span>  
  
4.  <span data-ttu-id="46bab-115">Если свойство для привязки не является одним из часто используемых свойств, нажмите кнопку **многоточие** кнопки (![экрана VisualStudioEllipsesButton](../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton") ) в **(Дополнительно)** поле для отображения **форматирование и дополнительная привязка** диалоговое окно с полный список свойств для этого элемента управления.</span><span class="sxs-lookup"><span data-stu-id="46bab-115">If the property you want to bind is not one of the commonly bound properties, click the **Ellipsis** button (![VisualStudioEllipsesButton screenshot](../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")) in the **(Advanced)** box to display the **Formatting and Advanced Binding** dialog box with a complete list of properties for that control.</span></span>  
  
5.  <span data-ttu-id="46bab-116">Выберите свойство для привязки и щелкните стрелку раскрывающегося списка под **привязки**.</span><span class="sxs-lookup"><span data-stu-id="46bab-116">Select the property you want to bind and click the drop-down arrow under **Binding**.</span></span>  
  
     <span data-ttu-id="46bab-117">Отобразится список доступных источников данных.</span><span class="sxs-lookup"><span data-stu-id="46bab-117">A list of available data sources is displayed.</span></span>  
  
6.  <span data-ttu-id="46bab-118">Разверните источник данных, к которому требуется привязаться, пока не найдете нужный одиночный элемент данных.</span><span class="sxs-lookup"><span data-stu-id="46bab-118">Expand the data source you want to bind to until you find the single data element you want.</span></span> <span data-ttu-id="46bab-119">Например, при привязке к значению столбца в таблице набора данных разверните имя набора данных, а затем разверните имя таблицы для отображения имен столбцов.</span><span class="sxs-lookup"><span data-stu-id="46bab-119">For example, if you are binding to a column value in a dataset's table, expand the name of the dataset, and then expand the table name to display column names.</span></span>  
  
7.  <span data-ttu-id="46bab-120">Щелкните имя элемента для привязки.</span><span class="sxs-lookup"><span data-stu-id="46bab-120">Click the name of an element to bind to.</span></span>  
  
8.  <span data-ttu-id="46bab-121">При работе **форматирование и дополнительная привязка** диалоговое окно, нажмите кнопку **ОК** для возврата **свойства** окна.</span><span class="sxs-lookup"><span data-stu-id="46bab-121">If you were working in the **Formatting and Advanced Binding** dialog box, click **OK** to return to the **Properties** window.</span></span>  
  
9. <span data-ttu-id="46bab-122">Если требуется выполнить привязку дополнительных свойств элемента управления, повторите шаги с 3 по 7.</span><span class="sxs-lookup"><span data-stu-id="46bab-122">If you want to bind additional properties of the control, repeat steps 3 through 7.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="46bab-123">Поскольку элементы управления с простой привязкой отображают только один элемент данных, очень типично Добавление логики переходов в форму Windows Forms с помощью элементов управления с простой привязкой.</span><span class="sxs-lookup"><span data-stu-id="46bab-123">Because simple-bound controls show only a single data element, it is very typical to include navigation logic in a Windows Form with simple-bound controls.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="46bab-124">См. также</span><span class="sxs-lookup"><span data-stu-id="46bab-124">See Also</span></span>  
 <xref:System.Windows.Forms.Binding>  
 [<span data-ttu-id="46bab-125">Привязка данных Windows Forms</span><span class="sxs-lookup"><span data-stu-id="46bab-125">Windows Forms Data Binding</span></span>](../../../docs/framework/winforms/windows-forms-data-binding.md)  
 [<span data-ttu-id="46bab-126">Привязка данных и Windows Forms</span><span class="sxs-lookup"><span data-stu-id="46bab-126">Data Binding and Windows Forms</span></span>](../../../docs/framework/winforms/data-binding-and-windows-forms.md)
