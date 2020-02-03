---
title: Как извлечь значок, связанный с файлом
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- displaying a file name and its file type icon in a ListView control [Windows Forms]
- file name extension icons [Windows Forms], displaying in a ListView
- extracting icons associated with a file type [Windows Forms]
ms.assetid: 88e2ad8b-c34f-415a-84f2-dad756b5c928
ms.openlocfilehash: 28769144b0e1c631a31c3c541747a6215f861d0e
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76742539"
---
# <a name="how-to-extract-the-icon-associated-with-a-file-in-windows-forms"></a><span data-ttu-id="15b27-102">Практическое руководство. Извлечение связанного с файлом значка в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="15b27-102">How to: Extract the Icon Associated with a File in Windows Forms</span></span>
<span data-ttu-id="15b27-103">Многие файлы имеют встроенные значки, которые предоставляют визуальное представление связанного типа файлов.</span><span class="sxs-lookup"><span data-stu-id="15b27-103">Many files have embedded icons that provide a visual representation of the associated file type.</span></span> <span data-ttu-id="15b27-104">Например, документы Microsoft Word содержат значок, который идентифицирует их как документы Word.</span><span class="sxs-lookup"><span data-stu-id="15b27-104">For example, Microsoft Word documents contain an icon that identifies them as Word documents.</span></span> <span data-ttu-id="15b27-105">При отображении файлов в элементе управления "список" или "Таблица" может потребоваться отобразить значок, представляющий тип файла рядом с каждым именем файла.</span><span class="sxs-lookup"><span data-stu-id="15b27-105">When displaying files in a list control or table control, you may want to display the icon representing the file type next to each file name.</span></span> <span data-ttu-id="15b27-106">Это можно легко сделать с помощью метода <xref:System.Drawing.Icon.ExtractAssociatedIcon%2A>.</span><span class="sxs-lookup"><span data-stu-id="15b27-106">You can do this easily by using the <xref:System.Drawing.Icon.ExtractAssociatedIcon%2A> method.</span></span>  
  
## <a name="example"></a><span data-ttu-id="15b27-107">Пример</span><span class="sxs-lookup"><span data-stu-id="15b27-107">Example</span></span>  
 <span data-ttu-id="15b27-108">В следующем примере кода показано, как извлечь значок, связанный с файлом, и отобразить имя файла и связанный с ним значок в элементе управления <xref:System.Windows.Forms.ListView>.</span><span class="sxs-lookup"><span data-stu-id="15b27-108">The following code example demonstrates how to extract the icon associated with a file and display the file name and its associated icon in a <xref:System.Windows.Forms.ListView> control.</span></span>  
  
 [!code-csharp[System.Drawing.Icon.ExtractAssociatedIconEx#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.Icon.ExtractAssociatedIconEx/CS/Form1.cs#1)]
 [!code-vb[System.Drawing.Icon.ExtractAssociatedIconEx#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.Icon.ExtractAssociatedIconEx/VB/Form1.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="15b27-109">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="15b27-109">Compiling the Code</span></span>  
 <span data-ttu-id="15b27-110">Чтобы скомпилировать пример:</span><span class="sxs-lookup"><span data-stu-id="15b27-110">To compile the example:</span></span>  
  
- <span data-ttu-id="15b27-111">Вставьте приведенный выше код в форму Windows Forms и вызовите метод `ExtractAssociatedIconExample` из конструктора формы или <xref:System.Windows.Forms.Form.Load> метода обработки событий.</span><span class="sxs-lookup"><span data-stu-id="15b27-111">Paste the preceding code into a Windows Form, and call the `ExtractAssociatedIconExample` method from the form's constructor or <xref:System.Windows.Forms.Form.Load> event-handling method.</span></span>  
  
     <span data-ttu-id="15b27-112">Необходимо убедиться, что форма импортирует пространство имен <xref:System.IO>.</span><span class="sxs-lookup"><span data-stu-id="15b27-112">You will need to make sure that your form imports the <xref:System.IO> namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="15b27-113">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="15b27-113">See also</span></span>

- [<span data-ttu-id="15b27-114">Изображения, точечные рисунки и метафайлы</span><span class="sxs-lookup"><span data-stu-id="15b27-114">Images, Bitmaps, and Metafiles</span></span>](images-bitmaps-and-metafiles.md)
- [<span data-ttu-id="15b27-115">Элемент управления ListView</span><span class="sxs-lookup"><span data-stu-id="15b27-115">ListView Control</span></span>](../controls/listview-control-windows-forms.md)
