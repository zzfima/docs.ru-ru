---
title: Метафайлы в GDI+
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- images [Windows Forms], metafiles
- GDI+, metafiles
- metafiles
ms.assetid: 51da872c-c783-440f-8bf6-1e580a966c31
ms.openlocfilehash: df54289722cf12bad840722c6eafdaa43279a5dc
ms.sourcegitcommit: b1cfd260928d464d91e20121f9bdba7611c94d71
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/02/2019
ms.locfileid: "67504586"
---
# <a name="metafiles-in-gdi"></a><span data-ttu-id="0a1c6-102">Метафайлы в GDI+</span><span class="sxs-lookup"><span data-stu-id="0a1c6-102">Metafiles in GDI+</span></span>
<span data-ttu-id="0a1c6-103">GDI + предоставляет <xref:System.Drawing.Imaging.Metafile> таким образом, чтобы можно было записывать и отображать метафайлы.</span><span class="sxs-lookup"><span data-stu-id="0a1c6-103">GDI+ provides the <xref:System.Drawing.Imaging.Metafile> class so that you can record and display metafiles.</span></span> <span data-ttu-id="0a1c6-104">Метафайл, также называемый векторного изображения, — это образ, который хранится в виде последовательности команд и параметров рисования.</span><span class="sxs-lookup"><span data-stu-id="0a1c6-104">A metafile, also called a vector image, is an image that is stored as a sequence of drawing commands and settings.</span></span> <span data-ttu-id="0a1c6-105">Команды и параметры, сохраненные в <xref:System.Drawing.Imaging.Metafile> объекта можно хранить в памяти или сохранить файл или поток.</span><span class="sxs-lookup"><span data-stu-id="0a1c6-105">The commands and settings recorded in a <xref:System.Drawing.Imaging.Metafile> object can be stored in memory or saved to a file or stream.</span></span>  
  
## <a name="metafile-formats"></a><span data-ttu-id="0a1c6-106">Метафайлы</span><span class="sxs-lookup"><span data-stu-id="0a1c6-106">Metafile Formats</span></span>  
 <span data-ttu-id="0a1c6-107">GDI + позволяет отображать метафайлы, сохраненные в следующих форматах:</span><span class="sxs-lookup"><span data-stu-id="0a1c6-107">GDI+ can display metafiles that have been stored in the following formats:</span></span>  
  
- <span data-ttu-id="0a1c6-108">Метафайл Windows (WMF)</span><span class="sxs-lookup"><span data-stu-id="0a1c6-108">Windows Metafile (WMF)</span></span>  
  
- <span data-ttu-id="0a1c6-109">EMF (Enhanced Metafile —расширенный метафайл)</span><span class="sxs-lookup"><span data-stu-id="0a1c6-109">Enhanced Metafile (EMF)</span></span>  
  
- <span data-ttu-id="0a1c6-110">EMF +</span><span class="sxs-lookup"><span data-stu-id="0a1c6-110">EMF+</span></span>  
  
 <span data-ttu-id="0a1c6-111">GDI + позволяет сохранять метафайлы в форматы EMF и EMF +, но не в формате WMF.</span><span class="sxs-lookup"><span data-stu-id="0a1c6-111">GDI+ can record metafiles in the EMF and EMF+ formats, but not in the WMF format.</span></span>  
  
 <span data-ttu-id="0a1c6-112">EMF + является расширением формата EMF, кроме записей GDI + для сохранения.</span><span class="sxs-lookup"><span data-stu-id="0a1c6-112">EMF+ is an extension to EMF that allows GDI+ records to be stored.</span></span> <span data-ttu-id="0a1c6-113">Существует две разновидности формат EMF +. EMF + только и EMF + Dual.</span><span class="sxs-lookup"><span data-stu-id="0a1c6-113">There are two variations on the EMF+ format: EMF+ Only and EMF+ Dual.</span></span> <span data-ttu-id="0a1c6-114">Метафайлы EMF + Only содержат только записи GDI +.</span><span class="sxs-lookup"><span data-stu-id="0a1c6-114">EMF+ Only metafiles contain only GDI+ records.</span></span> <span data-ttu-id="0a1c6-115">Такие метафайлы могут отображаться в GDI +, но не в GDI.</span><span class="sxs-lookup"><span data-stu-id="0a1c6-115">Such metafiles can be displayed by GDI+ but not by GDI.</span></span> <span data-ttu-id="0a1c6-116">Метафайлы EMF + Dual содержат записи GDI + и GDI.</span><span class="sxs-lookup"><span data-stu-id="0a1c6-116">EMF+ Dual metafiles contain GDI+ and GDI records.</span></span> <span data-ttu-id="0a1c6-117">Каждая запись GDI + в метафайле EMF + Dual сопряжен с альтернативной записью GDI.</span><span class="sxs-lookup"><span data-stu-id="0a1c6-117">Each GDI+ record in an EMF+ Dual metafile is paired with an alternate GDI record.</span></span> <span data-ttu-id="0a1c6-118">Такие метафайлы могут отображаться GDI или GDI +.</span><span class="sxs-lookup"><span data-stu-id="0a1c6-118">Such metafiles can be displayed by GDI+ or by GDI.</span></span>  
  
 <span data-ttu-id="0a1c6-119">В следующем примере отображается метафайл, который был ранее сохранен как файл.</span><span class="sxs-lookup"><span data-stu-id="0a1c6-119">The following example displays a metafile that was previously saved as a file.</span></span> <span data-ttu-id="0a1c6-120">Метафайл отображается с его верхнего левого угла в (100, 100).</span><span class="sxs-lookup"><span data-stu-id="0a1c6-120">The metafile is displayed with its upper-left corner at (100, 100).</span></span>  
  
 [!code-csharp[System.Drawing.ImagesBitmapsMetafiles#21](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ImagesBitmapsMetafiles/CS/Class1.cs#21)]
 [!code-vb[System.Drawing.ImagesBitmapsMetafiles#21](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ImagesBitmapsMetafiles/VB/Class1.vb#21)]  
  
## <a name="see-also"></a><span data-ttu-id="0a1c6-121">См. также</span><span class="sxs-lookup"><span data-stu-id="0a1c6-121">See also</span></span>

- [<span data-ttu-id="0a1c6-122">Изображения, точечные рисунки и метафайлы</span><span class="sxs-lookup"><span data-stu-id="0a1c6-122">Images, Bitmaps, and Metafiles</span></span>](images-bitmaps-and-metafiles.md)
