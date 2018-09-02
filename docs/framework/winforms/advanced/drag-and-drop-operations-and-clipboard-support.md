---
title: Операции перетаскивания и поддержка буфера обмена
ms.date: 03/30/2017
helpviewer_keywords:
- drag and drop [Windows Forms]
- drag and drop [Windows Forms], Windows Forms
- Clipboard [Windows Forms], Windows Forms
ms.assetid: 7cce79b6-5835-46fd-b690-73f12ad368b2
ms.openlocfilehash: c2bb3c24298ffe5308af03c5af5bae697a22c33b
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/01/2018
ms.locfileid: "43398636"
---
# <a name="drag-and-drop-operations-and-clipboard-support"></a><span data-ttu-id="f283f-102">Операции перетаскивания и поддержка буфера обмена</span><span class="sxs-lookup"><span data-stu-id="f283f-102">Drag-and-Drop Operations and Clipboard Support</span></span>
<span data-ttu-id="f283f-103">Пользовательские операции перетаскивания в приложении Windows можно включить путем обработки последовательности событий, в частности событий <xref:System.Windows.Forms.Control.DragEnter>, <xref:System.Windows.Forms.Control.DragLeave> и <xref:System.Windows.Forms.Control.DragDrop>.</span><span class="sxs-lookup"><span data-stu-id="f283f-103">You can enable user drag-and-drop operations within a Windows-based application by handling a series of events, most notably the <xref:System.Windows.Forms.Control.DragEnter>, <xref:System.Windows.Forms.Control.DragLeave>, and <xref:System.Windows.Forms.Control.DragDrop> events.</span></span>  
  
 <span data-ttu-id="f283f-104">Реализовать поддержку пользовательских операций вырезания, копирования, вставки и передачу данных пользователя в буфер обмена в приложении Windows также можно с помощью обычных вызовов методов.</span><span class="sxs-lookup"><span data-stu-id="f283f-104">You can also implement user cut/copy/paste support and user data transfer to the Clipboard within your Windows-based applications by using simple method calls.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="f283f-105">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="f283f-105">In This Section</span></span>  
 [<span data-ttu-id="f283f-106">Пример. Выполнение операции перетаскивания в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="f283f-106">Walkthrough: Performing a Drag-and-Drop Operation in Windows Forms</span></span>](../../../../docs/framework/winforms/advanced/walkthrough-performing-a-drag-and-drop-operation-in-windows-forms.md)  
 <span data-ttu-id="f283f-107">Описание запуска операции перетаскивания.</span><span class="sxs-lookup"><span data-stu-id="f283f-107">Explains how to start a drag-and-drop operation.</span></span>  
  
 [<span data-ttu-id="f283f-108">Практическое руководство. Выполнение операции перетаскивания между приложениями</span><span class="sxs-lookup"><span data-stu-id="f283f-108">How to: Perform Drag-and-Drop Operations Between Applications</span></span>](../../../../docs/framework/winforms/advanced/how-to-perform-drag-and-drop-operations-between-applications.md)  
 <span data-ttu-id="f283f-109">Демонстрация выполнения операций перетаскивания в разных приложениях.</span><span class="sxs-lookup"><span data-stu-id="f283f-109">Illustrates how to accomplish drag-and-drop operations across applications.</span></span>  
  
 [<span data-ttu-id="f283f-110">Практическое руководство. Добавление данных в буфер обмена</span><span class="sxs-lookup"><span data-stu-id="f283f-110">How to: Add Data to the Clipboard</span></span>](../../../../docs/framework/winforms/advanced/how-to-add-data-to-the-clipboard.md)  
 <span data-ttu-id="f283f-111">Описание программного способа вставки данных в буфер обмена.</span><span class="sxs-lookup"><span data-stu-id="f283f-111">Describes a way to programmatically insert information on the Clipboard.</span></span>  
  
 [<span data-ttu-id="f283f-112">Практическое руководство. Извлечение данных из буфера обмена</span><span class="sxs-lookup"><span data-stu-id="f283f-112">How to: Retrieve Data from the Clipboard</span></span>](../../../../docs/framework/winforms/advanced/how-to-retrieve-data-from-the-clipboard.md)  
 <span data-ttu-id="f283f-113">Описание способов получения доступа к данным, хранимым в буфере обмена.</span><span class="sxs-lookup"><span data-stu-id="f283f-113">Describes how to access the data stored on the Clipboard.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="f283f-114">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="f283f-114">Related Sections</span></span>  
 [<span data-ttu-id="f283f-115">Функциональная возможность перетаскивания в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="f283f-115">Drag-and-Drop Functionality in Windows Forms</span></span>](../../../../docs/framework/winforms/drag-and-drop-functionality-in-windows-forms.md)  
 <span data-ttu-id="f283f-116">Описание методов, событий и классов, используемых для реализации поведения перетаскивания.</span><span class="sxs-lookup"><span data-stu-id="f283f-116">Describes the methods, events, and classes used to implement drag-and-drop behavior.</span></span>  
  
 <xref:System.Windows.Forms.Control.QueryContinueDrag>  
 <span data-ttu-id="f283f-117">Описание особенностей события, которое запрашивает разрешение на продолжение операции перетаскивания.</span><span class="sxs-lookup"><span data-stu-id="f283f-117">Describes the intricacies of the event that asks permission to continue the drag operation.</span></span>  
  
 <xref:System.Windows.Forms.Control.DoDragDrop%2A>  
 <span data-ttu-id="f283f-118">Описание особенностей метода, который является основным для запуска операции перетаскивания.</span><span class="sxs-lookup"><span data-stu-id="f283f-118">Describes the intricacies of the method that is central to beginning a drag operation.</span></span>  
  
 <xref:System.Windows.Forms.Clipboard>  
 <span data-ttu-id="f283f-119">Также см. в разделе [как: отправка данных активной дочерней MDI-формы](https://msdn.microsoft.com/library/y0hkh2c8\(v=vs.110\)).</span><span class="sxs-lookup"><span data-stu-id="f283f-119">Also see [How to: Send Data to the Active MDI Child](https://msdn.microsoft.com/library/y0hkh2c8\(v=vs.110\)).</span></span>
