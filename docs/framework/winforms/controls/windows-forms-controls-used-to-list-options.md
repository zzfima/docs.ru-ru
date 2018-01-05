---
title: "Создание списка для выбора элементов в Windows Forms"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Windows Forms controls, listing options
- option lists in Windows Forms
ms.assetid: 5bc064c7-bc1f-4b62-8f4b-252f864b118e
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: f43e8982dc9caaa57ffb6865bf9988243f42fa8b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="windows-forms-controls-used-to-list-options"></a><span data-ttu-id="6f2ed-102">Создание списка для выбора элементов в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="6f2ed-102">Windows Forms Controls Used to List Options</span></span>
<span data-ttu-id="6f2ed-103">Если вы хотите предоставить пользователям список параметров для выбора можно добавить различные элементы управления в форму Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="6f2ed-103">You can add a variety of controls to a Windows Form if you want to provide users with a list of options to choose from.</span></span> <span data-ttu-id="6f2ed-104">В зависимости от того сколько вы хотите ограничить пользователей входных данных, можно добавить <xref:System.Windows.Forms.ListBox> управления <xref:System.Windows.Forms.ComboBox> управления, или <xref:System.Windows.Forms.CheckedListBox> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="6f2ed-104">Depending on how much you want to restrict your users' input, you can add a <xref:System.Windows.Forms.ListBox> control, a <xref:System.Windows.Forms.ComboBox> control, or a <xref:System.Windows.Forms.CheckedListBox> control.</span></span> <span data-ttu-id="6f2ed-105">Используйте следующие ссылки, чтобы определить, какой элемент управления следует соответствует вашим потребностям.</span><span class="sxs-lookup"><span data-stu-id="6f2ed-105">Use the following links to determine which control best suits your needs.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="6f2ed-106">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="6f2ed-106">In This Section</span></span>  
 [<span data-ttu-id="6f2ed-107">Применение элемента управления ComboBox вместо элемента управления ListBox в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="6f2ed-107">When to Use a Windows Forms ComboBox Instead of a ListBox</span></span>](../../../../docs/framework/winforms/controls/when-to-use-a-windows-forms-combobox-instead-of-a-listbox.md)  
 <span data-ttu-id="6f2ed-108">Корпорация Майкрософт рекомендует соответствующего основе списка элемента управления в зависимости от требований и ограничений формы Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="6f2ed-108">Recommends an appropriate list-based control depending on the needs and restrictions of your Windows Form.</span></span>  
  
 [<span data-ttu-id="6f2ed-109">Практическое руководство. Получение доступа к определенным элементам в элементах управления ComboBox, ListBox или CheckedListBox в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="6f2ed-109">How to: Access Specific Items in a Windows Forms ComboBox, ListBox, or CheckedListBox Control</span></span>](../../../../docs/framework/winforms/controls/access-specific-items-in-a-wf-combobox-listbox-or-checkedlistbox.md)  
 <span data-ttu-id="6f2ed-110">Инструкции по определению программными средствами, какой элемент в списке отображается в заданной позиции.</span><span class="sxs-lookup"><span data-stu-id="6f2ed-110">Gives instructions for programmatically determining which item in a list appears in a given position.</span></span>  
  
 [<span data-ttu-id="6f2ed-111">Практическое руководство. Добавление и удаление элементов, отображаемых в элементах управления ComboBox, ListBox и CheckedListBox в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="6f2ed-111">How to: Add and Remove Items from a Windows Forms ComboBox, ListBox, or CheckedListBox Control</span></span>](../../../../docs/framework/winforms/controls/add-and-remove-items-from-a-wf-combobox.md)  
 <span data-ttu-id="6f2ed-112">Инструкции для добавления или удаления элементов из списка элемента управления.</span><span class="sxs-lookup"><span data-stu-id="6f2ed-112">Gives instructions for adding or removing items from a control's list of items.</span></span>  
  
 [<span data-ttu-id="6f2ed-113">Практическое руководство. Создание таблицы подстановки для элемента управления ComboBox, ListBox или CheckedListBox в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="6f2ed-113">How to: Create a Lookup Table for a Windows Forms ComboBox, ListBox, or CheckedListBox Control</span></span>](../../../../docs/framework/winforms/controls/create-a-lookup-table-for-a-wf-combobox-listbox.md)  
 <span data-ttu-id="6f2ed-114">Инструкции по отображению и сохранению данных формы в нужных форматах.</span><span class="sxs-lookup"><span data-stu-id="6f2ed-114">Gives directions for displaying and storing form data in useful formats.</span></span>  
  
 [<span data-ttu-id="6f2ed-115">Практическое руководство. Связывание элемента управления ComboBox или ListBox с данными в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="6f2ed-115">How to: Bind a Windows Forms ComboBox or ListBox Control to Data</span></span>](../../../../docs/framework/winforms/controls/how-to-bind-a-windows-forms-combobox-or-listbox-control-to-data.md)  
 <span data-ttu-id="6f2ed-116">Указания по привязке элемента управления на основе списка к источнику данных.</span><span class="sxs-lookup"><span data-stu-id="6f2ed-116">Gives directions for binding a list-based control to a data source.</span></span>  
  
 [<span data-ttu-id="6f2ed-117">Практическое руководство. Сортировка содержимого элемента управления ComboBox, ListBox или CheckedListBox в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="6f2ed-117">How to: Sort the Contents of a Windows Forms ComboBox, ListBox, or CheckedListBox Control</span></span>](../../../../docs/framework/winforms/controls/sort-the-contents-of-a-wf-combobox-listbox-or-checkedlistbox-control.md)  
 <span data-ttu-id="6f2ed-118">Объясняется, как сортировать данные списка в источнике данных.</span><span class="sxs-lookup"><span data-stu-id="6f2ed-118">Explains how to sort list data at its data source.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="6f2ed-119">Ссылка</span><span class="sxs-lookup"><span data-stu-id="6f2ed-119">Reference</span></span>  
 <xref:System.Windows.Forms.CheckedListBox>  
 <span data-ttu-id="6f2ed-120">Описание класса и всех его членов.</span><span class="sxs-lookup"><span data-stu-id="6f2ed-120">Describes this class and has links to all its members.</span></span>  
  
 <xref:System.Windows.Forms.ComboBox>  
 <span data-ttu-id="6f2ed-121">Описание класса и всех его членов.</span><span class="sxs-lookup"><span data-stu-id="6f2ed-121">Describes this class and has links to all its members.</span></span>  
  
 <xref:System.Windows.Forms.ListBox>  
 <span data-ttu-id="6f2ed-122">Описание класса и всех его членов.</span><span class="sxs-lookup"><span data-stu-id="6f2ed-122">Describes this class and has links to all its members.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="6f2ed-123">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="6f2ed-123">Related Sections</span></span>  
 [<span data-ttu-id="6f2ed-124">Общие сведения об элементе управления CheckedListBox</span><span class="sxs-lookup"><span data-stu-id="6f2ed-124">CheckedListBox Control Overview</span></span>](../../../../docs/framework/winforms/controls/checkedlistbox-control-overview-windows-forms.md)  
 <span data-ttu-id="6f2ed-125">Описывается элемент управления, его основные возможности и свойства.</span><span class="sxs-lookup"><span data-stu-id="6f2ed-125">Explains what this control is and its key features and properties.</span></span>  
  
 [<span data-ttu-id="6f2ed-126">Общие сведения об элементе управления ComboBox</span><span class="sxs-lookup"><span data-stu-id="6f2ed-126">ComboBox Control Overview</span></span>](../../../../docs/framework/winforms/controls/combobox-control-overview-windows-forms.md)  
 <span data-ttu-id="6f2ed-127">Описывается элемент управления, его основные возможности и свойства.</span><span class="sxs-lookup"><span data-stu-id="6f2ed-127">Explains what this control is and its key features and properties.</span></span>  
  
 [<span data-ttu-id="6f2ed-128">Общие сведения об элементе управления ListBox</span><span class="sxs-lookup"><span data-stu-id="6f2ed-128">ListBox Control Overview</span></span>](../../../../docs/framework/winforms/controls/listbox-control-overview-windows-forms.md)  
 <span data-ttu-id="6f2ed-129">Описывается элемент управления, его основные возможности и свойства.</span><span class="sxs-lookup"><span data-stu-id="6f2ed-129">Explains what this control is and its key features and properties.</span></span>  
  
 [<span data-ttu-id="6f2ed-130">Элементы управления для использования в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="6f2ed-130">Controls to Use on Windows Forms</span></span>](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)  
 <span data-ttu-id="6f2ed-131">Полный список элементов управления Windows Forms со ссылками на информацию об их применении.</span><span class="sxs-lookup"><span data-stu-id="6f2ed-131">Provides a complete list of Windows Forms controls, with links to information on their use.</span></span>
