---
title: Операции перетаскивания и поддержка буфера обмена
ms.date: 03/30/2017
helpviewer_keywords:
- drag and drop [Windows Forms]
- drag and drop [Windows Forms], Windows Forms
- Clipboard [Windows Forms], Windows Forms
ms.assetid: 7cce79b6-5835-46fd-b690-73f12ad368b2
ms.openlocfilehash: 5e7bb75b648163dab7e410a159d55ebbb75f1b0a
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61756433"
---
# <a name="drag-and-drop-operations-and-clipboard-support"></a><span data-ttu-id="fcc0b-102">Операции перетаскивания и поддержка буфера обмена</span><span class="sxs-lookup"><span data-stu-id="fcc0b-102">Drag-and-Drop Operations and Clipboard Support</span></span>
<span data-ttu-id="fcc0b-103">Пользовательские операции перетаскивания в приложении Windows можно включить путем обработки последовательности событий, в частности событий <xref:System.Windows.Forms.Control.DragEnter>, <xref:System.Windows.Forms.Control.DragLeave> и <xref:System.Windows.Forms.Control.DragDrop>.</span><span class="sxs-lookup"><span data-stu-id="fcc0b-103">You can enable user drag-and-drop operations within a Windows-based application by handling a series of events, most notably the <xref:System.Windows.Forms.Control.DragEnter>, <xref:System.Windows.Forms.Control.DragLeave>, and <xref:System.Windows.Forms.Control.DragDrop> events.</span></span>  
  
 <span data-ttu-id="fcc0b-104">Реализовать поддержку пользовательских операций вырезания, копирования, вставки и передачу данных пользователя в буфер обмена в приложении Windows также можно с помощью обычных вызовов методов.</span><span class="sxs-lookup"><span data-stu-id="fcc0b-104">You can also implement user cut/copy/paste support and user data transfer to the Clipboard within your Windows-based applications by using simple method calls.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="fcc0b-105">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="fcc0b-105">In This Section</span></span>  
 [<span data-ttu-id="fcc0b-106">Пошаговое руководство: Выполнение операции перетаскивания и вставки в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="fcc0b-106">Walkthrough: Performing a Drag-and-Drop Operation in Windows Forms</span></span>](walkthrough-performing-a-drag-and-drop-operation-in-windows-forms.md)  
 <span data-ttu-id="fcc0b-107">Описание запуска операции перетаскивания.</span><span class="sxs-lookup"><span data-stu-id="fcc0b-107">Explains how to start a drag-and-drop operation.</span></span>  
  
 [<span data-ttu-id="fcc0b-108">Практическое руководство. Выполнение операции перетаскивания и вставки между приложениями</span><span class="sxs-lookup"><span data-stu-id="fcc0b-108">How to: Perform Drag-and-Drop Operations Between Applications</span></span>](how-to-perform-drag-and-drop-operations-between-applications.md)  
 <span data-ttu-id="fcc0b-109">Демонстрация выполнения операций перетаскивания в разных приложениях.</span><span class="sxs-lookup"><span data-stu-id="fcc0b-109">Illustrates how to accomplish drag-and-drop operations across applications.</span></span>  
  
 [<span data-ttu-id="fcc0b-110">Практическое руководство. Добавление данных в буфер обмена</span><span class="sxs-lookup"><span data-stu-id="fcc0b-110">How to: Add Data to the Clipboard</span></span>](how-to-add-data-to-the-clipboard.md)  
 <span data-ttu-id="fcc0b-111">Описание программного способа вставки данных в буфер обмена.</span><span class="sxs-lookup"><span data-stu-id="fcc0b-111">Describes a way to programmatically insert information on the Clipboard.</span></span>  
  
 [<span data-ttu-id="fcc0b-112">Практическое руководство. Получить данные из буфера обмена</span><span class="sxs-lookup"><span data-stu-id="fcc0b-112">How to: Retrieve Data from the Clipboard</span></span>](how-to-retrieve-data-from-the-clipboard.md)  
 <span data-ttu-id="fcc0b-113">Описание способов получения доступа к данным, хранимым в буфере обмена.</span><span class="sxs-lookup"><span data-stu-id="fcc0b-113">Describes how to access the data stored on the Clipboard.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="fcc0b-114">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="fcc0b-114">Related Sections</span></span>  
 [<span data-ttu-id="fcc0b-115">Функциональная возможность перетаскивания в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="fcc0b-115">Drag-and-Drop Functionality in Windows Forms</span></span>](../drag-and-drop-functionality-in-windows-forms.md)  
 <span data-ttu-id="fcc0b-116">Описание методов, событий и классов, используемых для реализации поведения перетаскивания.</span><span class="sxs-lookup"><span data-stu-id="fcc0b-116">Describes the methods, events, and classes used to implement drag-and-drop behavior.</span></span>  
  
 <xref:System.Windows.Forms.Control.QueryContinueDrag>  
 <span data-ttu-id="fcc0b-117">Описание особенностей события, которое запрашивает разрешение на продолжение операции перетаскивания.</span><span class="sxs-lookup"><span data-stu-id="fcc0b-117">Describes the intricacies of the event that asks permission to continue the drag operation.</span></span>  
  
 <xref:System.Windows.Forms.Control.DoDragDrop%2A>  
 <span data-ttu-id="fcc0b-118">Описание особенностей метода, который является основным для запуска операции перетаскивания.</span><span class="sxs-lookup"><span data-stu-id="fcc0b-118">Describes the intricacies of the method that is central to beginning a drag operation.</span></span>  
  
 <xref:System.Windows.Forms.Clipboard>  
 <span data-ttu-id="fcc0b-119">Также см. раздел [Как Отправки данных в активную дочернюю форму MDI](how-to-send-data-to-the-active-mdi-child.md).</span><span class="sxs-lookup"><span data-stu-id="fcc0b-119">Also see [How to: Send Data to the Active MDI Child](how-to-send-data-to-the-active-mdi-child.md).</span></span>
