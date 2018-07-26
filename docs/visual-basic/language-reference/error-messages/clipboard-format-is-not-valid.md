---
title: Недопустимый формат буфера обмена
ms.date: 07/20/2015
f1_keywords:
- vbrID460
ms.assetid: 71a4a045-65bb-417d-b3bd-99a9fa3c53f6
ms.openlocfilehash: f2a0ab33c1749117d5de4987e85c44602ccd29ce
ms.sourcegitcommit: 70c76a12449439bac0f7a359866be5a0311ce960
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/25/2018
ms.locfileid: "39245562"
---
# <a name="clipboard-format-is-not-valid"></a><span data-ttu-id="df3e7-102">Недопустимый формат буфера обмена</span><span class="sxs-lookup"><span data-stu-id="df3e7-102">Clipboard format is not valid</span></span>
<span data-ttu-id="df3e7-103">Указанный формат буфера обмена не совместим с выполняемый метод.</span><span class="sxs-lookup"><span data-stu-id="df3e7-103">The specified Clipboard format is incompatible with the method being executed.</span></span> <span data-ttu-id="df3e7-104">Среди возможных причин этой ошибки:</span><span class="sxs-lookup"><span data-stu-id="df3e7-104">Among the possible causes for this error are:</span></span>  
  
-   <span data-ttu-id="df3e7-105">Использование буфера обмена `GetText` или `SetText` метод с формат буфера обмена, отличных от `vbCFText` или `vbCFLink`.</span><span class="sxs-lookup"><span data-stu-id="df3e7-105">Using the Clipboard's `GetText` or `SetText` method with a Clipboard format other than `vbCFText` or `vbCFLink`.</span></span>  
  
-   <span data-ttu-id="df3e7-106">Использование буфера обмена `GetData` или `SetData` метод с формат буфера обмена, отличных от `vbCFBitmap`, `vbCFDIB`, или `vbCFMetafile`.</span><span class="sxs-lookup"><span data-stu-id="df3e7-106">Using the Clipboard's `GetData` or `SetData` method with a Clipboard format other than `vbCFBitmap`, `vbCFDIB`, or `vbCFMetafile`.</span></span>  
  
-   <span data-ttu-id="df3e7-107">С помощью `GetData` или `SetData` методы `DataObject` с формат буфера обмена в диапазоне, зарезервированной с помощью Microsoft Windows для зарегистрированных форматов (& HC000 - & HFFFF), при этом формат буфера обмена не был зарегистрирован с помощью Microsoft Windows .</span><span class="sxs-lookup"><span data-stu-id="df3e7-107">Using the `GetData` or `SetData` methods of a `DataObject` with a Clipboard format in the range reserved by Microsoft Windows for registered formats (&HC000-&HFFFF), when that Clipboard format has not been registered with Microsoft Windows.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="df3e7-108">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="df3e7-108">To correct this error</span></span>  
  
-   <span data-ttu-id="df3e7-109">Удалите недопустимый формат и укажите допустимый.</span><span class="sxs-lookup"><span data-stu-id="df3e7-109">Remove the invalid format and specify a valid one.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="df3e7-110">См. также</span><span class="sxs-lookup"><span data-stu-id="df3e7-110">See Also</span></span>  
 [<span data-ttu-id="df3e7-111">Буфер обмена. Добавление других форматов</span><span class="sxs-lookup"><span data-stu-id="df3e7-111">Clipboard: Adding Other Formats</span></span>](/cpp/mfc/clipboard-adding-other-formats)
