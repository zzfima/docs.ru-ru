---
title: "Практическое руководство. Добавление данных в буфер обмена"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Clipboard [Windows Forms], copying data to
- data [Windows Forms], copying to Clipboard
ms.assetid: 25152454-0e78-40a9-8a9e-a2a5a274e517
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 452dfc5a9645e8f43ab583099deec60faa2d1b4d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-add-data-to-the-clipboard"></a><span data-ttu-id="8256c-102">Практическое руководство. Добавление данных в буфер обмена</span><span class="sxs-lookup"><span data-stu-id="8256c-102">How to: Add Data to the Clipboard</span></span>
<span data-ttu-id="8256c-103"><xref:System.Windows.Forms.Clipboard> Класс предоставляет методы, которые можно использовать для взаимодействия с компонентом буфер обмена операционной системы Windows.</span><span class="sxs-lookup"><span data-stu-id="8256c-103">The <xref:System.Windows.Forms.Clipboard> class provides methods that you can use to interact with the Windows operating system Clipboard feature.</span></span> <span data-ttu-id="8256c-104">Многие приложения используют буфер обмена в качестве временного хранилища данных.</span><span class="sxs-lookup"><span data-stu-id="8256c-104">Many applications use the Clipboard as a temporary repository for data.</span></span> <span data-ttu-id="8256c-105">Например текстовые редакторы использовать буфер обмена во время операций вырезания и вставки.</span><span class="sxs-lookup"><span data-stu-id="8256c-105">For example, word processors use the Clipboard during cut-and-paste operations.</span></span> <span data-ttu-id="8256c-106">Буфер обмена также полезен для передачи данных из одного приложения в другое.</span><span class="sxs-lookup"><span data-stu-id="8256c-106">The Clipboard is also useful for transferring data from one application to another.</span></span>  
  
 <span data-ttu-id="8256c-107">При добавлении данных в буфер обмена, чтобы другие приложения могли распознать данные, если они могут использовать этот формат можно указать формат данных.</span><span class="sxs-lookup"><span data-stu-id="8256c-107">When you add data to the Clipboard, you can indicate the data format so that other applications can recognize the data if they can use that format.</span></span> <span data-ttu-id="8256c-108">Можно также добавлять данные в буфер обмена в нескольких различных форматах, чтобы увеличить количество других приложений, которые потенциально могут использовать данные.</span><span class="sxs-lookup"><span data-stu-id="8256c-108">You can also add data to the Clipboard in multiple different formats to increase the number of other applications that can potentially use the data.</span></span>  
  
 <span data-ttu-id="8256c-109">Формат буфера обмена является строка, определяющая формат, чтобы приложение, использующее этот формат может получать связанные данные.</span><span class="sxs-lookup"><span data-stu-id="8256c-109">A Clipboard format is a string that identifies the format so that an application that uses that format can retrieve the associated data.</span></span> <span data-ttu-id="8256c-110"><xref:System.Windows.Forms.DataFormats> Класс предоставляет имена стандартных форматов для использования.</span><span class="sxs-lookup"><span data-stu-id="8256c-110">The <xref:System.Windows.Forms.DataFormats> class provides predefined format names for your use.</span></span> <span data-ttu-id="8256c-111">Можно также использовать собственные имена форматов или использовать тип объекта в качестве его формата.</span><span class="sxs-lookup"><span data-stu-id="8256c-111">You can also use your own format names or use the type of an object as its format.</span></span>  
  
 <span data-ttu-id="8256c-112">Чтобы добавить данные в буфер обмена в один или несколько форматов, используйте <xref:System.Windows.Forms.Clipboard.SetDataObject%2A> метод.</span><span class="sxs-lookup"><span data-stu-id="8256c-112">To add data to the Clipboard in one or multiple formats, use the <xref:System.Windows.Forms.Clipboard.SetDataObject%2A> method.</span></span> <span data-ttu-id="8256c-113">Этот метод можно передать любой объект, но для добавления данных в нескольких форматах, необходимо добавить данные отдельный объект, предназначенный для работы с несколькими форматами.</span><span class="sxs-lookup"><span data-stu-id="8256c-113">You can pass any object to this method, but to add data in multiple formats, you must first add the data to a separate object designed to work with multiple formats.</span></span> <span data-ttu-id="8256c-114">Как правило, вы добавите данные не будут <xref:System.Windows.Forms.DataObject>, но можно использовать любой тип, реализующий <xref:System.Windows.Forms.IDataObject> интерфейса.</span><span class="sxs-lookup"><span data-stu-id="8256c-114">Typically, you will add your data to a <xref:System.Windows.Forms.DataObject>, but you can use any type that implements the <xref:System.Windows.Forms.IDataObject> interface.</span></span>  
  
 <span data-ttu-id="8256c-115">В [!INCLUDE[dnprdnext](../../../../includes/dnprdnext-md.md)], можно добавить данные непосредственно в буфер обмена с помощью новых методов, позволяющих упростить основные задачи в буфер обмена.</span><span class="sxs-lookup"><span data-stu-id="8256c-115">In [!INCLUDE[dnprdnext](../../../../includes/dnprdnext-md.md)], you can add data directly to the Clipboard by using new methods designed to make basic Clipboard tasks easier.</span></span> <span data-ttu-id="8256c-116">Эти методы можно используйте при работе с данными в одном общем формате такие как текст.</span><span class="sxs-lookup"><span data-stu-id="8256c-116">Use these methods when you work with data in a single, common format such as text.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8256c-117">Все приложения Windows используют один буфер обмена.</span><span class="sxs-lookup"><span data-stu-id="8256c-117">All Windows-based applications share the Clipboard.</span></span> <span data-ttu-id="8256c-118">Таким образом содержимое могут быть изменены при переходе в другое приложение.</span><span class="sxs-lookup"><span data-stu-id="8256c-118">Therefore, the contents are subject to change when you switch to another application.</span></span>  
>   
>  <span data-ttu-id="8256c-119"><xref:System.Windows.Forms.Clipboard> Класс может использоваться только в потоках в режим однопотоковое подразделение (STA).</span><span class="sxs-lookup"><span data-stu-id="8256c-119">The <xref:System.Windows.Forms.Clipboard> class can only be used in threads set to single thread apartment (STA) mode.</span></span> <span data-ttu-id="8256c-120">Чтобы использовать этот класс, убедитесь, что ваш `Main` метод помечен атрибутом <xref:System.STAThreadAttribute> атрибута.</span><span class="sxs-lookup"><span data-stu-id="8256c-120">To use this class, ensure that your `Main` method is marked with the <xref:System.STAThreadAttribute> attribute.</span></span>  
>   
>  <span data-ttu-id="8256c-121">Объект должен поддерживать сериализацию для помещения в буфер обмена.</span><span class="sxs-lookup"><span data-stu-id="8256c-121">An object must be serializable for it to be put on the Clipboard.</span></span> <span data-ttu-id="8256c-122">Чтобы сделать тип сериализуемым, его необходимо пометить <xref:System.SerializableAttribute> атрибута.</span><span class="sxs-lookup"><span data-stu-id="8256c-122">To make a type serializable, mark it with the <xref:System.SerializableAttribute> attribute.</span></span> <span data-ttu-id="8256c-123">Если методу буфера обмена передается несериализуемый объект, метод завершится с ошибкой без вызова исключения.</span><span class="sxs-lookup"><span data-stu-id="8256c-123">If you pass a non-serializable object to a Clipboard method, the method will fail without throwing an exception.</span></span> <span data-ttu-id="8256c-124">Дополнительные сведения о сериализации см. в разделе <xref:System.Runtime.Serialization>.</span><span class="sxs-lookup"><span data-stu-id="8256c-124">For more information about serialization, see <xref:System.Runtime.Serialization>.</span></span>  
  
### <a name="to-add-data-to-the-clipboard-in-a-single-common-format"></a><span data-ttu-id="8256c-125">Чтобы добавить данные в буфер обмена в одном общем формате</span><span class="sxs-lookup"><span data-stu-id="8256c-125">To add data to the Clipboard in a single, common format</span></span>  
  
1.  <span data-ttu-id="8256c-126">Используйте <xref:System.Windows.Forms.Clipboard.SetAudio%2A>, <xref:System.Windows.Forms.Clipboard.SetFileDropList%2A>, <xref:System.Windows.Forms.Clipboard.SetImage%2A>, или <xref:System.Windows.Forms.Clipboard.SetText%2A> метод.</span><span class="sxs-lookup"><span data-stu-id="8256c-126">Use the <xref:System.Windows.Forms.Clipboard.SetAudio%2A>, <xref:System.Windows.Forms.Clipboard.SetFileDropList%2A>, <xref:System.Windows.Forms.Clipboard.SetImage%2A>, or <xref:System.Windows.Forms.Clipboard.SetText%2A> method.</span></span> <span data-ttu-id="8256c-127">Эти методы доступны только в [!INCLUDE[dnprdnext](../../../../includes/dnprdnext-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8256c-127">These methods are available only in [!INCLUDE[dnprdnext](../../../../includes/dnprdnext-md.md)].</span></span>  
  
     [!code-csharp[System.Windows.Forms.Clipboard#2](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/CS/form1.cs#2)]
     [!code-vb[System.Windows.Forms.Clipboard#2](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/vb/form1.vb#2)]  
  
### <a name="to-add-data-to-the-clipboard-in-a-custom-format"></a><span data-ttu-id="8256c-128">Чтобы добавить данные в буфер обмена в пользовательском формате</span><span class="sxs-lookup"><span data-stu-id="8256c-128">To add data to the Clipboard in a custom format</span></span>  
  
1.  <span data-ttu-id="8256c-129">Используйте <xref:System.Windows.Forms.Clipboard.SetData%2A> метод с именем пользовательского формата.</span><span class="sxs-lookup"><span data-stu-id="8256c-129">Use the <xref:System.Windows.Forms.Clipboard.SetData%2A> method with a custom format name.</span></span> <span data-ttu-id="8256c-130">Этот метод доступен только в [!INCLUDE[dnprdnext](../../../../includes/dnprdnext-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8256c-130">This method is available only in [!INCLUDE[dnprdnext](../../../../includes/dnprdnext-md.md)].</span></span>  
  
     <span data-ttu-id="8256c-131">Можно также использовать имена стандартных форматов с <xref:System.Windows.Forms.Clipboard.SetData%2A> метод.</span><span class="sxs-lookup"><span data-stu-id="8256c-131">You can also use predefined format names with the <xref:System.Windows.Forms.Clipboard.SetData%2A> method.</span></span> <span data-ttu-id="8256c-132">Дополнительные сведения см. в разделе <xref:System.Windows.Forms.DataFormats>.</span><span class="sxs-lookup"><span data-stu-id="8256c-132">For more information, see <xref:System.Windows.Forms.DataFormats>.</span></span>  
  
     [!code-csharp[System.Windows.Forms.Clipboard#3](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/CS/form1.cs#3)]
     [!code-vb[System.Windows.Forms.Clipboard#3](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/vb/form1.vb#3)]  
    [!code-csharp[System.Windows.Forms.Clipboard#100](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/CS/form1.cs#100)]
    [!code-vb[System.Windows.Forms.Clipboard#100](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/vb/form1.vb#100)]  
  
### <a name="to-add-data-to-the-clipboard-in-multiple-formats"></a><span data-ttu-id="8256c-133">Чтобы добавить данные в буфер обмена в нескольких форматах</span><span class="sxs-lookup"><span data-stu-id="8256c-133">To add data to the Clipboard in multiple formats</span></span>  
  
1.  <span data-ttu-id="8256c-134">Используйте <xref:System.Windows.Forms.Clipboard.SetDataObject%2A> метод и передайте его в <xref:System.Windows.Forms.DataObject> , содержащий нужные данные.</span><span class="sxs-lookup"><span data-stu-id="8256c-134">Use the <xref:System.Windows.Forms.Clipboard.SetDataObject%2A> method and pass in a <xref:System.Windows.Forms.DataObject> that contains your data.</span></span> <span data-ttu-id="8256c-135">Необходимо использовать этот метод для добавления данных в буфер обмена для версий более ранних, чем [!INCLUDE[dnprdnlong](../../../../includes/dnprdnlong-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8256c-135">You must use this method to add data to the Clipboard on versions earlier than [!INCLUDE[dnprdnlong](../../../../includes/dnprdnlong-md.md)].</span></span>  
  
     [!code-csharp[System.Windows.Forms.Clipboard#4](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/CS/form1.cs#4)]
     [!code-vb[System.Windows.Forms.Clipboard#4](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/vb/form1.vb#4)]  
    [!code-csharp[System.Windows.Forms.Clipboard#100](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/CS/form1.cs#100)]
    [!code-vb[System.Windows.Forms.Clipboard#100](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/vb/form1.vb#100)]  
  
## <a name="see-also"></a><span data-ttu-id="8256c-136">См. также</span><span class="sxs-lookup"><span data-stu-id="8256c-136">See Also</span></span>  
 [<span data-ttu-id="8256c-137">Операции перетаскивания и поддержка буфера обмена</span><span class="sxs-lookup"><span data-stu-id="8256c-137">Drag-and-Drop Operations and Clipboard Support</span></span>](../../../../docs/framework/winforms/advanced/drag-and-drop-operations-and-clipboard-support.md)  
 [<span data-ttu-id="8256c-138">Практическое руководство. Извлечение данных из буфера обмена</span><span class="sxs-lookup"><span data-stu-id="8256c-138">How to: Retrieve Data from the Clipboard</span></span>](../../../../docs/framework/winforms/advanced/how-to-retrieve-data-from-the-clipboard.md)
