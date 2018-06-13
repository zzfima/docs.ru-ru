---
title: Недопустимый формат буфера обмена
ms.date: 07/20/2015
f1_keywords:
- vbrID460
ms.assetid: 71a4a045-65bb-417d-b3bd-99a9fa3c53f6
ms.openlocfilehash: eef16096b269902dbaca6a344abf4c5f6a504fb7
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33586225"
---
# <a name="clipboard-format-is-not-valid"></a><span data-ttu-id="e9eba-102">Недопустимый формат буфера обмена</span><span class="sxs-lookup"><span data-stu-id="e9eba-102">Clipboard format is not valid</span></span>
<span data-ttu-id="e9eba-103">Указанный формат буфера обмена не совместим с выполняемый метод.</span><span class="sxs-lookup"><span data-stu-id="e9eba-103">The specified Clipboard format is incompatible with the method being executed.</span></span> <span data-ttu-id="e9eba-104">Среди возможных причин этой ошибки являются:</span><span class="sxs-lookup"><span data-stu-id="e9eba-104">Among the possible causes for this error are:</span></span>  
  
-   <span data-ttu-id="e9eba-105">Использование буфера обмена `GetText` или `SetText` метод с форматом буфера обмена, отличным от `vbCFText` или `vbCFLink`.</span><span class="sxs-lookup"><span data-stu-id="e9eba-105">Using the Clipboard's `GetText` or `SetText` method with a Clipboard format other than `vbCFText` or `vbCFLink`.</span></span>  
  
-   <span data-ttu-id="e9eba-106">Использование буфера обмена `GetData` или `SetData` метод с форматом буфера обмена, отличным от `vbCFBitmap`, `vbCFDIB`, или `vbCFMetafile`.</span><span class="sxs-lookup"><span data-stu-id="e9eba-106">Using the Clipboard's `GetData` or `SetData` method with a Clipboard format other than `vbCFBitmap`, `vbCFDIB`, or `vbCFMetafile`.</span></span>  
  
-   <span data-ttu-id="e9eba-107">С помощью `DataObject``GetData` метода или `SetData` метод с форматом буфера обмена в диапазоне, зарезервированном Microsoft Windows для зарегистрированных форматов (& HC000 - & HFFFF), при этом формат буфера обмена не был зарегистрирован с Microsoft Windows.</span><span class="sxs-lookup"><span data-stu-id="e9eba-107">Using the `DataObject``GetData` method or `SetData` method with a Clipboard format in the range reserved by Microsoft Windows for registered formats (&HC000-&HFFFF), when that Clipboard format has not been registered with Microsoft Windows.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="e9eba-108">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="e9eba-108">To correct this error</span></span>  
  
-   <span data-ttu-id="e9eba-109">Удалите недопустимый формат и укажите допустимый.</span><span class="sxs-lookup"><span data-stu-id="e9eba-109">Remove the invalid format and specify a valid one.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e9eba-110">См. также</span><span class="sxs-lookup"><span data-stu-id="e9eba-110">See Also</span></span>  
 [<span data-ttu-id="e9eba-111">Буфер обмена. Добавление других форматов</span><span class="sxs-lookup"><span data-stu-id="e9eba-111">Clipboard: Adding Other Formats</span></span>](/cpp/mfc/clipboard-adding-other-formats)
