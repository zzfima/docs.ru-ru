---
title: "Практическое руководство. Создание связанного элемента управления и форматирование отображаемых данных"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- data [Windows Forms], formatting
- bound controls [Windows Forms], creating
- bound controls [Windows Forms], formatting data
ms.assetid: d5a56228-899d-41d9-8af8-87b3f4ec2f94
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: a8c2836d841215ed3ca8e04461b1298cd41287de
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-create-a-bound-control-and-format-the-displayed-data"></a><span data-ttu-id="5d57e-102">Практическое руководство. Создание связанного элемента управления и форматирование отображаемых данных</span><span class="sxs-lookup"><span data-stu-id="5d57e-102">How to: Create a Bound Control and Format the Displayed Data</span></span>
<span data-ttu-id="5d57e-103">Благодаря функции привязки данных Windows Forms можно форматировать данные, отображаемые в элементе управления с привязкой к данным с помощью **форматирование и дополнительная привязка** диалоговое окно.</span><span class="sxs-lookup"><span data-stu-id="5d57e-103">With Windows Forms data binding, you can format the data displayed in a data-bound control by using the **Formatting and Advanced Binding** dialog box.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5d57e-104">Отображаемые диалоговые окна и команды меню могут отличаться от описанных в справке в зависимости от текущих параметров или выпуска.</span><span class="sxs-lookup"><span data-stu-id="5d57e-104">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="5d57e-105">Чтобы изменить параметры, выберите в меню **Сервис** пункт **Импорт и экспорт параметров** .</span><span class="sxs-lookup"><span data-stu-id="5d57e-105">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="5d57e-106">Дополнительные сведения см. в статье [Настройка параметров разработки в Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span><span class="sxs-lookup"><span data-stu-id="5d57e-106">For more information, see [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span></span>  
  
### <a name="to-bind-a-control-and-format-the-displayed-data"></a><span data-ttu-id="5d57e-107">Привязка элемента управления и форматирование отображаемых данных</span><span class="sxs-lookup"><span data-stu-id="5d57e-107">To bind a control and format the displayed data</span></span>  
  
1.  <span data-ttu-id="5d57e-108">Подключение к источнику данных.</span><span class="sxs-lookup"><span data-stu-id="5d57e-108">Connect to a data source.</span></span>  
  
     <span data-ttu-id="5d57e-109">Дополнительные сведения см. в разделе [соединение с источником данных](../../../docs/framework/data/adonet/connecting-to-a-data-source.md).</span><span class="sxs-lookup"><span data-stu-id="5d57e-109">For more information, see [Connecting to a Data Source](../../../docs/framework/data/adonet/connecting-to-a-data-source.md).</span></span>  
  
2.  <span data-ttu-id="5d57e-110">Выберите элемент управления в форме и откройте окно "Свойства".</span><span class="sxs-lookup"><span data-stu-id="5d57e-110">In the form, select the control, and then open the Properties window.</span></span>  
  
3.  <span data-ttu-id="5d57e-111">Разверните **(DataBindings)** свойства, а затем в **(Дополнительно)** нажмите кнопку с многоточием (![экрана VisualStudioEllipsesButton] (../../../docs/framework/winforms/media/vbellipsesbutton.png " vbEllipsesButton")) для отображения **форматирование и дополнительная привязка** dialog box, в котором содержится полный список свойств этого элемента управления.</span><span class="sxs-lookup"><span data-stu-id="5d57e-111">Expand the **(DataBindings)** property, and then in the **(Advanced)** box, click the ellipsis button (![VisualStudioEllipsesButton screenshot](../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")) to display the **Formatting and Advanced Binding** dialog box, which has a complete list of properties for that control.</span></span>  
  
4.  <span data-ttu-id="5d57e-112">Выберите свойство для привязки, а затем нажмите кнопку **привязки** стрелка.</span><span class="sxs-lookup"><span data-stu-id="5d57e-112">Select the property you want to bind, and then click the **Binding** arrow.</span></span>  
  
     <span data-ttu-id="5d57e-113">Отобразится список доступных источников данных.</span><span class="sxs-lookup"><span data-stu-id="5d57e-113">A list of available data sources is displayed.</span></span>  
  
5.  <span data-ttu-id="5d57e-114">Разверните источник данных, к которому требуется привязаться, пока не найдете нужный одиночный элемент данных.</span><span class="sxs-lookup"><span data-stu-id="5d57e-114">Expand the data source you want to bind to until you find the single data element you want.</span></span>  
  
     <span data-ttu-id="5d57e-115">Например, при привязке к значению столбца в таблице набора данных разверните имя набора данных, а затем разверните имя таблицы для отображения имен столбцов.</span><span class="sxs-lookup"><span data-stu-id="5d57e-115">For example, if you are binding to a column value in a dataset's table, expand the name of the dataset, and then expand the table name to display column names.</span></span>  
  
6.  <span data-ttu-id="5d57e-116">Щелкните имя элемента для привязки.</span><span class="sxs-lookup"><span data-stu-id="5d57e-116">Click the name of an element to bind to.</span></span>  
  
7.  <span data-ttu-id="5d57e-117">В **форматирования типа** выберите формат, который следует применить к данным, отображаемых в элементе управления.</span><span class="sxs-lookup"><span data-stu-id="5d57e-117">In the **Format type** box, click the format you want to apply to the data displayed in the control.</span></span>  
  
     <span data-ttu-id="5d57e-118">В каждом случае можно указать значение, отображаемое в элементе управления, если источник данных содержит <xref:System.DBNull>.</span><span class="sxs-lookup"><span data-stu-id="5d57e-118">In every case, you can specify the value displayed in the control if the data source contains <xref:System.DBNull>.</span></span> <span data-ttu-id="5d57e-119">В противном случае параметры будут немного отличаться в зависимости от выбранного типа формата.</span><span class="sxs-lookup"><span data-stu-id="5d57e-119">Otherwise, the options vary slightly, depending on the format type you choose.</span></span> <span data-ttu-id="5d57e-120">В таблице ниже приведены типы форматов и параметры.</span><span class="sxs-lookup"><span data-stu-id="5d57e-120">The following table shows the format types and options.</span></span>  
  
    |<span data-ttu-id="5d57e-121">Тип формата</span><span class="sxs-lookup"><span data-stu-id="5d57e-121">Format type</span></span>|<span data-ttu-id="5d57e-122">Параметр форматирования</span><span class="sxs-lookup"><span data-stu-id="5d57e-122">Formatting option</span></span>|  
    |-----------------|-----------------------|  
    |<span data-ttu-id="5d57e-123">Без форматирования</span><span class="sxs-lookup"><span data-stu-id="5d57e-123">No Formatting</span></span>|<span data-ttu-id="5d57e-124">Параметры отсутствуют.</span><span class="sxs-lookup"><span data-stu-id="5d57e-124">No options.</span></span>|  
    |<span data-ttu-id="5d57e-125">Numeric</span><span class="sxs-lookup"><span data-stu-id="5d57e-125">Numeric</span></span>|<span data-ttu-id="5d57e-126">Укажите число знаков после запятой, используя **десятичных разрядов** вверх / вниз '.</span><span class="sxs-lookup"><span data-stu-id="5d57e-126">Specify number of decimal places by using **Decimal places** up-down control.</span></span>|  
    |<span data-ttu-id="5d57e-127">Валюта</span><span class="sxs-lookup"><span data-stu-id="5d57e-127">Currency</span></span>|<span data-ttu-id="5d57e-128">Укажите число знаков после запятой, используя **десятичных разрядов** вверх / вниз '.</span><span class="sxs-lookup"><span data-stu-id="5d57e-128">Specify number of decimal places by using **Decimal places** up-down control.</span></span>|  
    |<span data-ttu-id="5d57e-129">Дата/время</span><span class="sxs-lookup"><span data-stu-id="5d57e-129">Date Time</span></span>|<span data-ttu-id="5d57e-130">Выберите способ отображения даты и времени, выбрав один из элементов в **типа** поля выбора.</span><span class="sxs-lookup"><span data-stu-id="5d57e-130">Select how the date and time should be displayed by selecting one of the items in the **Type** selection box.</span></span>|  
    |<span data-ttu-id="5d57e-131">Экспоненциальный</span><span class="sxs-lookup"><span data-stu-id="5d57e-131">Scientific</span></span>|<span data-ttu-id="5d57e-132">Укажите число знаков после запятой, используя **десятичных разрядов** вверх / вниз '.</span><span class="sxs-lookup"><span data-stu-id="5d57e-132">Specify number of decimal places by using **Decimal places** up-down control.</span></span>|  
    |<span data-ttu-id="5d57e-133">Пользовательский</span><span class="sxs-lookup"><span data-stu-id="5d57e-133">Custom</span></span>|<span data-ttu-id="5d57e-134">Укажите используемую строку пользовательского формата.</span><span class="sxs-lookup"><span data-stu-id="5d57e-134">Specify a custom format string using.</span></span><br /><br /> <span data-ttu-id="5d57e-135">Дополнительные сведения см. в разделе [типы форматирования](../../../docs/standard/base-types/formatting-types.md).</span><span class="sxs-lookup"><span data-stu-id="5d57e-135">For more information, see [Formatting Types](../../../docs/standard/base-types/formatting-types.md).</span></span> <span data-ttu-id="5d57e-136">**Примечание:** строки настраиваемого формата, не обязательно успешно кругового пути между источником данных и связанным элементом управления.</span><span class="sxs-lookup"><span data-stu-id="5d57e-136">**Note:**  Custom format strings are not guaranteed to successfully round trip between the data source and bound control.</span></span> <span data-ttu-id="5d57e-137">Вместо них в коде обработки событий для привязки и применения пользовательских форматов обрабатывайте событие <xref:System.Windows.Forms.Binding.Parse> или <xref:System.Windows.Forms.Binding.Format>.</span><span class="sxs-lookup"><span data-stu-id="5d57e-137">Instead handle the <xref:System.Windows.Forms.Binding.Parse> or <xref:System.Windows.Forms.Binding.Format> event for the binding and apply custom formatting in the event-handling code.</span></span>|  
  
8.  <span data-ttu-id="5d57e-138">Нажмите кнопку **ОК** закрыть **форматирование и дополнительная привязка** диалоговое окно и вернуться в окне «Свойства».</span><span class="sxs-lookup"><span data-stu-id="5d57e-138">Click **OK** to close the **Formatting and Advanced Binding** dialog box and return to the Properties window.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5d57e-139">См. также</span><span class="sxs-lookup"><span data-stu-id="5d57e-139">See Also</span></span>  
 [<span data-ttu-id="5d57e-140">Практическое руководство. Создание элемента управления с простой привязкой в форме Windows Forms</span><span class="sxs-lookup"><span data-stu-id="5d57e-140">How to: Create a Simple-Bound Control on a Windows Form</span></span>](../../../docs/framework/winforms/how-to-create-a-simple-bound-control-on-a-windows-form.md)  
 [<span data-ttu-id="5d57e-141">Проверка введенных пользователем данных в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="5d57e-141">User Input Validation in Windows Forms</span></span>](../../../docs/framework/winforms/user-input-validation-in-windows-forms.md)  
 [<span data-ttu-id="5d57e-142">Привязка данных Windows Forms</span><span class="sxs-lookup"><span data-stu-id="5d57e-142">Windows Forms Data Binding</span></span>](../../../docs/framework/winforms/windows-forms-data-binding.md)
