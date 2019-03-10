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
ms.openlocfilehash: 25ce3fdd98560aba0918431bb77d6f3f23a04784
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/09/2019
ms.locfileid: "57722468"
---
# <a name="metafiles-in-gdi"></a><span data-ttu-id="fb48f-102">Метафайлы в GDI+</span><span class="sxs-lookup"><span data-stu-id="fb48f-102">Metafiles in GDI+</span></span>
[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] <span data-ttu-id="fb48f-103">предоставляет <xref:System.Drawing.Imaging.Metafile> таким образом, чтобы можно было записывать и отображать метафайлы.</span><span class="sxs-lookup"><span data-stu-id="fb48f-103">provides the <xref:System.Drawing.Imaging.Metafile> class so that you can record and display metafiles.</span></span> <span data-ttu-id="fb48f-104">Метафайл, также называемый векторного изображения, — это образ, который хранится в виде последовательности команд и параметров рисования.</span><span class="sxs-lookup"><span data-stu-id="fb48f-104">A metafile, also called a vector image, is an image that is stored as a sequence of drawing commands and settings.</span></span> <span data-ttu-id="fb48f-105">Команды и параметры, сохраненные в <xref:System.Drawing.Imaging.Metafile> объекта можно хранить в памяти или сохранить файл или поток.</span><span class="sxs-lookup"><span data-stu-id="fb48f-105">The commands and settings recorded in a <xref:System.Drawing.Imaging.Metafile> object can be stored in memory or saved to a file or stream.</span></span>  
  
## <a name="metafile-formats"></a><span data-ttu-id="fb48f-106">Метафайлы</span><span class="sxs-lookup"><span data-stu-id="fb48f-106">Metafile Formats</span></span>  
 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] <span data-ttu-id="fb48f-107">позволяет отображать метафайлы, сохраненные в следующих форматах:</span><span class="sxs-lookup"><span data-stu-id="fb48f-107">can display metafiles that have been stored in the following formats:</span></span>  
  
-   <span data-ttu-id="fb48f-108">Метафайл Windows (WMF)</span><span class="sxs-lookup"><span data-stu-id="fb48f-108">Windows Metafile (WMF)</span></span>  
  
-   <span data-ttu-id="fb48f-109">EMF (Enhanced Metafile —расширенный метафайл)</span><span class="sxs-lookup"><span data-stu-id="fb48f-109">Enhanced Metafile (EMF)</span></span>  
  
-   <span data-ttu-id="fb48f-110">EMF +</span><span class="sxs-lookup"><span data-stu-id="fb48f-110">EMF+</span></span>  
  
 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] <span data-ttu-id="fb48f-111">позволяет сохранять метафайлы в форматы EMF и EMF +, но не в формате WMF.</span><span class="sxs-lookup"><span data-stu-id="fb48f-111">can record metafiles in the EMF and EMF+ formats, but not in the WMF format.</span></span>  
  
 <span data-ttu-id="fb48f-112">EMF + является расширением формата EMF, [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] записи для сохранения.</span><span class="sxs-lookup"><span data-stu-id="fb48f-112">EMF+ is an extension to EMF that allows [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] records to be stored.</span></span> <span data-ttu-id="fb48f-113">Существует две разновидности формат EMF +. EMF + только и EMF + Dual.</span><span class="sxs-lookup"><span data-stu-id="fb48f-113">There are two variations on the EMF+ format: EMF+ Only and EMF+ Dual.</span></span> <span data-ttu-id="fb48f-114">Метафайлы EMF + Only содержат только [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] записей.</span><span class="sxs-lookup"><span data-stu-id="fb48f-114">EMF+ Only metafiles contain only [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] records.</span></span> <span data-ttu-id="fb48f-115">Такие метафайлы могут отображаться путем [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] , но не по [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)].</span><span class="sxs-lookup"><span data-stu-id="fb48f-115">Such metafiles can be displayed by [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] but not by [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)].</span></span> <span data-ttu-id="fb48f-116">Метафайлы EMF + Dual содержат [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] и [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] записей.</span><span class="sxs-lookup"><span data-stu-id="fb48f-116">EMF+ Dual metafiles contain [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] and [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] records.</span></span> <span data-ttu-id="fb48f-117">Каждый [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] запись EMF + Dual метафайла, вместе с альтернативной [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] записи.</span><span class="sxs-lookup"><span data-stu-id="fb48f-117">Each [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] record in an EMF+ Dual metafile is paired with an alternate [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] record.</span></span> <span data-ttu-id="fb48f-118">Такие метафайлы могут отображаться путем [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] или [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)].</span><span class="sxs-lookup"><span data-stu-id="fb48f-118">Such metafiles can be displayed by [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] or by [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)].</span></span>  
  
 <span data-ttu-id="fb48f-119">В следующем примере отображается метафайл, который был ранее сохранен как файл.</span><span class="sxs-lookup"><span data-stu-id="fb48f-119">The following example displays a metafile that was previously saved as a file.</span></span> <span data-ttu-id="fb48f-120">Метафайл отображается с его верхнего левого угла в (100, 100).</span><span class="sxs-lookup"><span data-stu-id="fb48f-120">The metafile is displayed with its upper-left corner at (100, 100).</span></span>  
  
 [!code-csharp[System.Drawing.ImagesBitmapsMetafiles#21](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ImagesBitmapsMetafiles/CS/Class1.cs#21)]
 [!code-vb[System.Drawing.ImagesBitmapsMetafiles#21](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ImagesBitmapsMetafiles/VB/Class1.vb#21)]  
  
## <a name="see-also"></a><span data-ttu-id="fb48f-121">См. также</span><span class="sxs-lookup"><span data-stu-id="fb48f-121">See also</span></span>
- [<span data-ttu-id="fb48f-122">Изображения, точечные рисунки и метафайлы</span><span class="sxs-lookup"><span data-stu-id="fb48f-122">Images, Bitmaps, and Metafiles</span></span>](images-bitmaps-and-metafiles.md)
