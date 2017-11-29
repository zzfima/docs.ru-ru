---
title: "Практическое руководство. Извлечение данных из буфера обмена"
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
- pasting Clipboard data
- Clipboard [Windows Forms], retrieving data
ms.assetid: 99612537-2c8a-449f-aab5-2b3b28d656e7
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: c2f71c6738f19e70826b95626377097de0cd9b3b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-retrieve-data-from-the-clipboard"></a><span data-ttu-id="1cb4a-102">Практическое руководство. Извлечение данных из буфера обмена</span><span class="sxs-lookup"><span data-stu-id="1cb4a-102">How to: Retrieve Data from the Clipboard</span></span>
<span data-ttu-id="1cb4a-103"><xref:System.Windows.Forms.Clipboard> Класс предоставляет методы, которые можно использовать для взаимодействия с компонентом буфер обмена операционной системы Windows.</span><span class="sxs-lookup"><span data-stu-id="1cb4a-103">The <xref:System.Windows.Forms.Clipboard> class provides methods that you can use to interact with the Windows operating system Clipboard feature.</span></span> <span data-ttu-id="1cb4a-104">Многие приложения используют буфер обмена в качестве временного хранилища данных.</span><span class="sxs-lookup"><span data-stu-id="1cb4a-104">Many applications use the Clipboard as a temporary repository for data.</span></span> <span data-ttu-id="1cb4a-105">Например текстовые редакторы использовать буфер обмена во время операций вырезания и вставки.</span><span class="sxs-lookup"><span data-stu-id="1cb4a-105">For example, word processors use the Clipboard during cut-and-paste operations.</span></span> <span data-ttu-id="1cb4a-106">Буфер обмена также полезен для передачи данных из одного приложения в другое.</span><span class="sxs-lookup"><span data-stu-id="1cb4a-106">The Clipboard is also useful for transferring information from one application to another.</span></span>  
  
 <span data-ttu-id="1cb4a-107">Некоторые приложения сохраняют данные в буфер обмена в нескольких форматах, чтобы увеличить количество других приложений, которые потенциально могут использовать данные.</span><span class="sxs-lookup"><span data-stu-id="1cb4a-107">Some applications store data on the Clipboard in multiple formats to increase the number of other applications that can potentially use the data.</span></span> <span data-ttu-id="1cb4a-108">Формат буфера обмена является строкой, которая определяет формат.</span><span class="sxs-lookup"><span data-stu-id="1cb4a-108">A Clipboard format is a string that identifies the format.</span></span> <span data-ttu-id="1cb4a-109">Приложение, использующее указанный формат можно получить связанные данные в буфер обмена.</span><span class="sxs-lookup"><span data-stu-id="1cb4a-109">An application that uses the identified format can retrieve the associated data on the Clipboard.</span></span> <span data-ttu-id="1cb4a-110"><xref:System.Windows.Forms.DataFormats> Класс предоставляет имена стандартных форматов для использования.</span><span class="sxs-lookup"><span data-stu-id="1cb4a-110">The <xref:System.Windows.Forms.DataFormats> class provides predefined format names for your use.</span></span> <span data-ttu-id="1cb4a-111">Можно также использовать собственные имена форматов или использовать тип объекта в качестве его формата.</span><span class="sxs-lookup"><span data-stu-id="1cb4a-111">You can also use your own format names or use an object's type as its format.</span></span> <span data-ttu-id="1cb4a-112">Сведения о добавлении данных в буфер обмена см. в разделе [как: добавить данные в буфер обмена](../../../../docs/framework/winforms/advanced/how-to-add-data-to-the-clipboard.md).</span><span class="sxs-lookup"><span data-stu-id="1cb4a-112">For information about adding data to the Clipboard, see [How to: Add Data to the Clipboard](../../../../docs/framework/winforms/advanced/how-to-add-data-to-the-clipboard.md).</span></span>  
  
 <span data-ttu-id="1cb4a-113">Чтобы определить, содержит ли буфер данных в определенном формате, используйте один из `Contains` *формат* методы или <xref:System.Windows.Forms.Clipboard.GetData%2A> метод.</span><span class="sxs-lookup"><span data-stu-id="1cb4a-113">To determine whether the Clipboard contains data in a particular format, use one of the `Contains`*Format* methods or the <xref:System.Windows.Forms.Clipboard.GetData%2A> method.</span></span> <span data-ttu-id="1cb4a-114">Для получения данных из буфера обмена, используйте один из `Get` *формат* методы или <xref:System.Windows.Forms.Clipboard.GetData%2A> метод.</span><span class="sxs-lookup"><span data-stu-id="1cb4a-114">To retrieve data from the Clipboard, use one of the `Get`*Format* methods or the <xref:System.Windows.Forms.Clipboard.GetData%2A> method.</span></span> <span data-ttu-id="1cb4a-115">Эти методы являются новыми в [!INCLUDE[dnprdnext](../../../../includes/dnprdnext-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1cb4a-115">These methods are new in [!INCLUDE[dnprdnext](../../../../includes/dnprdnext-md.md)].</span></span>  
  
 <span data-ttu-id="1cb4a-116">Для доступа к данным из буфера обмена с помощью версии более ранней, чем [!INCLUDE[dnprdnlong](../../../../includes/dnprdnlong-md.md)], используйте <xref:System.Windows.Forms.Clipboard.GetDataObject%2A> метод и вызывать методы возвращаемого <xref:System.Windows.Forms.IDataObject>.</span><span class="sxs-lookup"><span data-stu-id="1cb4a-116">To access data from the Clipboard by using versions earlier than [!INCLUDE[dnprdnlong](../../../../includes/dnprdnlong-md.md)], use the <xref:System.Windows.Forms.Clipboard.GetDataObject%2A> method and call the methods of the returned <xref:System.Windows.Forms.IDataObject>.</span></span> <span data-ttu-id="1cb4a-117">Чтобы определить, доступен ли определенный формат в возвращаемом объекте, например, вызов <xref:System.Windows.Forms.IDataObject.GetDataPresent%2A> метод.</span><span class="sxs-lookup"><span data-stu-id="1cb4a-117">To determine whether a particular format is available in the returned object, for example, call the <xref:System.Windows.Forms.IDataObject.GetDataPresent%2A> method.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1cb4a-118">Все приложения, на основе Windows используют буфер обмена системы.</span><span class="sxs-lookup"><span data-stu-id="1cb4a-118">All Windows-based applications share the system Clipboard.</span></span> <span data-ttu-id="1cb4a-119">Таким образом содержимое могут быть изменены при переходе в другое приложение.</span><span class="sxs-lookup"><span data-stu-id="1cb4a-119">Therefore, the contents are subject to change when you switch to another application.</span></span>  
>   
>  <span data-ttu-id="1cb4a-120"><xref:System.Windows.Forms.Clipboard> Класс может использоваться только в потоках в режим однопотоковое подразделение (STA).</span><span class="sxs-lookup"><span data-stu-id="1cb4a-120">The <xref:System.Windows.Forms.Clipboard> class can only be used in threads set to single thread apartment (STA) mode.</span></span> <span data-ttu-id="1cb4a-121">Чтобы использовать этот класс, убедитесь, что ваш `Main` метод помечен атрибутом <xref:System.STAThreadAttribute> атрибута.</span><span class="sxs-lookup"><span data-stu-id="1cb4a-121">To use this class, ensure that your `Main` method is marked with the <xref:System.STAThreadAttribute> attribute.</span></span>  
  
### <a name="to-retrieve-data-from-the-clipboard-in-a-single-common-format"></a><span data-ttu-id="1cb4a-122">Для получения данных из буфера обмена в одном общем формате</span><span class="sxs-lookup"><span data-stu-id="1cb4a-122">To retrieve data from the Clipboard in a single, common format</span></span>  
  
1.  <span data-ttu-id="1cb4a-123">Используйте <xref:System.Windows.Forms.Clipboard.GetAudioStream%2A>, <xref:System.Windows.Forms.Clipboard.GetFileDropList%2A>, <xref:System.Windows.Forms.Clipboard.GetImage%2A>, или <xref:System.Windows.Forms.Clipboard.GetText%2A> метод.</span><span class="sxs-lookup"><span data-stu-id="1cb4a-123">Use the <xref:System.Windows.Forms.Clipboard.GetAudioStream%2A>, <xref:System.Windows.Forms.Clipboard.GetFileDropList%2A>, <xref:System.Windows.Forms.Clipboard.GetImage%2A>, or <xref:System.Windows.Forms.Clipboard.GetText%2A> method.</span></span> <span data-ttu-id="1cb4a-124">При необходимости используйте соответствующий `Contains` *формат* методы, чтобы определить, доступен ли данные в определенном формате.</span><span class="sxs-lookup"><span data-stu-id="1cb4a-124">Optionally, use the corresponding `Contains`*Format* methods first to determine whether data is available in a particular format.</span></span> <span data-ttu-id="1cb4a-125">Эти методы доступны только в [!INCLUDE[dnprdnext](../../../../includes/dnprdnext-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1cb4a-125">These methods are available only in [!INCLUDE[dnprdnext](../../../../includes/dnprdnext-md.md)].</span></span>  
  
     [!code-csharp[System.Windows.Forms.Clipboard#2](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/CS/form1.cs#2)]
     [!code-vb[System.Windows.Forms.Clipboard#2](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/vb/form1.vb#2)]  
  
### <a name="to-retrieve-data-from-the-clipboard-in-a-custom-format"></a><span data-ttu-id="1cb4a-126">Для получения данных из буфера обмена в пользовательском формате</span><span class="sxs-lookup"><span data-stu-id="1cb4a-126">To retrieve data from the Clipboard in a custom format</span></span>  
  
1.  <span data-ttu-id="1cb4a-127">Используйте <xref:System.Windows.Forms.Clipboard.GetData%2A> метод с именем пользовательского формата.</span><span class="sxs-lookup"><span data-stu-id="1cb4a-127">Use the <xref:System.Windows.Forms.Clipboard.GetData%2A> method with a custom format name.</span></span> <span data-ttu-id="1cb4a-128">Этот метод доступен только в [!INCLUDE[dnprdnext](../../../../includes/dnprdnext-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1cb4a-128">This method is available only in [!INCLUDE[dnprdnext](../../../../includes/dnprdnext-md.md)].</span></span>  
  
     <span data-ttu-id="1cb4a-129">Можно также использовать имена стандартных форматов с <xref:System.Windows.Forms.Clipboard.SetData%2A> метод.</span><span class="sxs-lookup"><span data-stu-id="1cb4a-129">You can also use predefined format names with the <xref:System.Windows.Forms.Clipboard.SetData%2A> method.</span></span> <span data-ttu-id="1cb4a-130">Для получения дополнительной информации см. <xref:System.Windows.Forms.DataFormats>.</span><span class="sxs-lookup"><span data-stu-id="1cb4a-130">For more information, see <xref:System.Windows.Forms.DataFormats>.</span></span>  
  
     [!code-csharp[System.Windows.Forms.Clipboard#3](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/CS/form1.cs#3)]
     [!code-vb[System.Windows.Forms.Clipboard#3](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/vb/form1.vb#3)]  
    [!code-csharp[System.Windows.Forms.Clipboard#100](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/CS/form1.cs#100)]
    [!code-vb[System.Windows.Forms.Clipboard#100](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/vb/form1.vb#100)]  
  
### <a name="to-retrieve-data-from-the-clipboard-in-multiple-formats"></a><span data-ttu-id="1cb4a-131">Для получения данных из буфера обмена в нескольких форматах</span><span class="sxs-lookup"><span data-stu-id="1cb4a-131">To retrieve data from the Clipboard in multiple formats</span></span>  
  
1.  <span data-ttu-id="1cb4a-132">Воспользуйтесь методом <xref:System.Windows.Forms.Clipboard.GetDataObject%2A>.</span><span class="sxs-lookup"><span data-stu-id="1cb4a-132">Use the <xref:System.Windows.Forms.Clipboard.GetDataObject%2A> method.</span></span> <span data-ttu-id="1cb4a-133">Необходимо использовать этот метод для извлечения данных из буфера обмена для версий более ранних, чем [!INCLUDE[dnprdnlong](../../../../includes/dnprdnlong-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1cb4a-133">You must use this method to retrieve data from the Clipboard on versions earlier than [!INCLUDE[dnprdnlong](../../../../includes/dnprdnlong-md.md)].</span></span>  
  
     [!code-csharp[System.Windows.Forms.Clipboard#4](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/CS/form1.cs#4)]
     [!code-vb[System.Windows.Forms.Clipboard#4](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/vb/form1.vb#4)]  
    [!code-csharp[System.Windows.Forms.Clipboard#100](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/CS/form1.cs#100)]
    [!code-vb[System.Windows.Forms.Clipboard#100](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/vb/form1.vb#100)]  
  
## <a name="see-also"></a><span data-ttu-id="1cb4a-134">См. также</span><span class="sxs-lookup"><span data-stu-id="1cb4a-134">See Also</span></span>  
 [<span data-ttu-id="1cb4a-135">Операции перетаскивания и поддержка буфера обмена</span><span class="sxs-lookup"><span data-stu-id="1cb4a-135">Drag-and-Drop Operations and Clipboard Support</span></span>](../../../../docs/framework/winforms/advanced/drag-and-drop-operations-and-clipboard-support.md)  
 [<span data-ttu-id="1cb4a-136">Практическое руководство. Добавление данных в буфер обмена</span><span class="sxs-lookup"><span data-stu-id="1cb4a-136">How to: Add Data to the Clipboard</span></span>](../../../../docs/framework/winforms/advanced/how-to-add-data-to-the-clipboard.md)
