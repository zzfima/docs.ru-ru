---
title: "Как создать объект данных"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataObject class [WPF], creating
- data objects [WPF], creating
- drag-and-drop [WPF], creating data objects
ms.assetid: 022fa142-717d-4fea-a53c-3b52e9d91aff
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 014d5229026a6fdaab203c82932742c7b2c7639e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-create-a-data-object"></a><span data-ttu-id="45805-102">Как создать объект данных</span><span class="sxs-lookup"><span data-stu-id="45805-102">How to: Create a Data Object</span></span>
<span data-ttu-id="45805-103">Следующие примеры демонстрируют различные способы создания объекта данных с помощью конструкторов, предоставляемые <xref:System.Windows.DataObject> класса.</span><span class="sxs-lookup"><span data-stu-id="45805-103">The following examples show various ways to create a data object using the constructors provided by the <xref:System.Windows.DataObject> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="45805-104">Пример</span><span class="sxs-lookup"><span data-stu-id="45805-104">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="45805-105">Описание:</span><span class="sxs-lookup"><span data-stu-id="45805-105">Description</span></span>  
 <span data-ttu-id="45805-106">В следующем примере кода создается новый объект данных и использует один из перегруженных конструкторов (<xref:System.Windows.DataObject.%23ctor%28System.Object%29>) для инициализации объекта данных со строкой.</span><span class="sxs-lookup"><span data-stu-id="45805-106">The following example code creates a new data object and uses one of the overloaded constructors (<xref:System.Windows.DataObject.%23ctor%28System.Object%29>) to initialize the data object with a string.</span></span>  <span data-ttu-id="45805-107">В этом случае соответствующий формат данных определяется автоматически в соответствии с типом хранимых данных, и по умолчанию разрешено автоматическое преобразование сохраненных данных.</span><span class="sxs-lookup"><span data-stu-id="45805-107">In this case, an appropriate data format is determined automatically according to the stored data's type, and auto-converting of the stored data is allowed by default.</span></span>  
  
### <a name="code"></a><span data-ttu-id="45805-108">Код</span><span class="sxs-lookup"><span data-stu-id="45805-108">Code</span></span>  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_Simple](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_createdataobject_simple)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_Simple](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_createdataobject_simple)]  
  
### <a name="description"></a><span data-ttu-id="45805-109">Описание:</span><span class="sxs-lookup"><span data-stu-id="45805-109">Description</span></span>  
 <span data-ttu-id="45805-110">Следующий пример кода представляет собой сжатую версию приведенного выше кода.</span><span class="sxs-lookup"><span data-stu-id="45805-110">The following example code is a condensed version of the code shown above.</span></span>  
  
### <a name="code"></a><span data-ttu-id="45805-111">Код</span><span class="sxs-lookup"><span data-stu-id="45805-111">Code</span></span>  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_Simple_Condensed](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_createdataobject_simple_condensed)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_Simple_Condensed](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_createdataobject_simple_condensed)]  
  
## <a name="example"></a><span data-ttu-id="45805-112">Пример</span><span class="sxs-lookup"><span data-stu-id="45805-112">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="45805-113">Описание:</span><span class="sxs-lookup"><span data-stu-id="45805-113">Description</span></span>  
 <span data-ttu-id="45805-114">В следующем примере кода создается новый объект данных и использует один из перегруженных конструкторов (<xref:System.Windows.DataObject.%23ctor%28System.String%2CSystem.Object%29>) для инициализации объекта данных со строкой и указанного формата данных.</span><span class="sxs-lookup"><span data-stu-id="45805-114">The following example code creates a new data object and uses one of the overloaded constructors (<xref:System.Windows.DataObject.%23ctor%28System.String%2CSystem.Object%29>) to initialize the data object with a string and a specified data format.</span></span>  <span data-ttu-id="45805-115">В этом случае формат данных задается строкой. <xref:System.Windows.DataFormats> класс предоставляет набор строк предопределенных типов.</span><span class="sxs-lookup"><span data-stu-id="45805-115">In this case the data format is specified by a string; the <xref:System.Windows.DataFormats> class provides a set of pre-defined type strings.</span></span> <span data-ttu-id="45805-116">Автоматическое преобразование сохраненных данных по умолчанию разрешено.</span><span class="sxs-lookup"><span data-stu-id="45805-116">Auto-converting of the stored data is allowed by default.</span></span>  
  
### <a name="code"></a><span data-ttu-id="45805-117">Код</span><span class="sxs-lookup"><span data-stu-id="45805-117">Code</span></span>  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_TypeString](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_createdataobject_typestring)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_TypeString](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_createdataobject_typestring)]  
  
### <a name="description"></a><span data-ttu-id="45805-118">Описание:</span><span class="sxs-lookup"><span data-stu-id="45805-118">Description</span></span>  
 <span data-ttu-id="45805-119">Следующий пример кода представляет собой сжатую версию приведенного выше кода.</span><span class="sxs-lookup"><span data-stu-id="45805-119">The following example code is a condensed version of the code shown above.</span></span>  
  
### <a name="code"></a><span data-ttu-id="45805-120">Код</span><span class="sxs-lookup"><span data-stu-id="45805-120">Code</span></span>  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_TypeString_Condensed](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_createdataobject_typestring_condensed)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_TypeString_Condensed](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_createdataobject_typestring_condensed)]  
  
## <a name="example"></a><span data-ttu-id="45805-121">Пример</span><span class="sxs-lookup"><span data-stu-id="45805-121">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="45805-122">Описание:</span><span class="sxs-lookup"><span data-stu-id="45805-122">Description</span></span>  
 <span data-ttu-id="45805-123">В следующем примере кода создается новый объект данных и использует один из перегруженных конструкторов (<xref:System.Windows.DataObject.%23ctor%2A>) для инициализации объекта данных со строкой и указанного формата данных.</span><span class="sxs-lookup"><span data-stu-id="45805-123">The following example code creates a new data object and uses one of the overloaded constructors (<xref:System.Windows.DataObject.%23ctor%2A>) to initialize the data object with a string and a specified data format.</span></span>  <span data-ttu-id="45805-124">В этом случае формат данных задается <xref:System.Type> параметра.</span><span class="sxs-lookup"><span data-stu-id="45805-124">In this case the data format is specified by a <xref:System.Type> parameter.</span></span>  <span data-ttu-id="45805-125">Автоматическое преобразование сохраненных данных по умолчанию разрешено.</span><span class="sxs-lookup"><span data-stu-id="45805-125">Auto-converting of the stored data is allowed by default.</span></span>  
  
### <a name="code"></a><span data-ttu-id="45805-126">Код</span><span class="sxs-lookup"><span data-stu-id="45805-126">Code</span></span>  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_Type](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_createdataobject_type)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_Type](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_createdataobject_type)]  
  
### <a name="description"></a><span data-ttu-id="45805-127">Описание:</span><span class="sxs-lookup"><span data-stu-id="45805-127">Description</span></span>  
 <span data-ttu-id="45805-128">Следующий пример кода представляет собой сжатую версию приведенного выше кода.</span><span class="sxs-lookup"><span data-stu-id="45805-128">The following example code is a condensed version of the code shown above.</span></span>  
  
### <a name="code"></a><span data-ttu-id="45805-129">Код</span><span class="sxs-lookup"><span data-stu-id="45805-129">Code</span></span>  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_Type_Condensed](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_createdataobject_type_condensed)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_Type_Condensed](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_createdataobject_type_condensed)]  
  
## <a name="example"></a><span data-ttu-id="45805-130">Пример</span><span class="sxs-lookup"><span data-stu-id="45805-130">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="45805-131">Описание:</span><span class="sxs-lookup"><span data-stu-id="45805-131">Description</span></span>  
 <span data-ttu-id="45805-132">В следующем примере кода создается новый объект данных и использует один из перегруженных конструкторов (<xref:System.Windows.DataObject.%23ctor%28System.String%2CSystem.Object%2CSystem.Boolean%29>) для инициализации объекта данных со строкой и указанного формата данных.</span><span class="sxs-lookup"><span data-stu-id="45805-132">The following example code creates a new data object and uses one of the overloaded constructors (<xref:System.Windows.DataObject.%23ctor%28System.String%2CSystem.Object%2CSystem.Boolean%29>) to initialize the data object with a string and a specified data format.</span></span>  <span data-ttu-id="45805-133">В этом случае формат данных задается строкой. <xref:System.Windows.DataFormats> класс предоставляет набор строк предопределенных типов.</span><span class="sxs-lookup"><span data-stu-id="45805-133">In this case the data format is specified by a string; the <xref:System.Windows.DataFormats> class provides a set of pre-defined type strings.</span></span> <span data-ttu-id="45805-134">Этот перегруженный конструктор позволяет вызывающему объекту укажите, разрешено ли автоматическое преобразование.</span><span class="sxs-lookup"><span data-stu-id="45805-134">This particular constructor overload enables the caller to specify whether auto-converting is allowed.</span></span>  
  
### <a name="code"></a><span data-ttu-id="45805-135">Код</span><span class="sxs-lookup"><span data-stu-id="45805-135">Code</span></span>  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_AutoConvert](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_createdataobject_autoconvert)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_AutoConvert](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_createdataobject_autoconvert)]  
  
### <a name="description"></a><span data-ttu-id="45805-136">Описание:</span><span class="sxs-lookup"><span data-stu-id="45805-136">Description</span></span>  
 <span data-ttu-id="45805-137">Следующий пример кода представляет собой сжатую версию приведенного выше кода.</span><span class="sxs-lookup"><span data-stu-id="45805-137">The following example code is a condensed version of the code shown above.</span></span>  
  
### <a name="code"></a><span data-ttu-id="45805-138">Код</span><span class="sxs-lookup"><span data-stu-id="45805-138">Code</span></span>  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_AutoConvert_Condensed](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_createdataobject_autoconvert_condensed)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_AutoConvert_Condensed](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_createdataobject_autoconvert_condensed)]  
  
## <a name="see-also"></a><span data-ttu-id="45805-139">См. также</span><span class="sxs-lookup"><span data-stu-id="45805-139">See Also</span></span>  
 <xref:System.Windows.IDataObject>
