---
title: Недопустимый формат буфера обмена
ms.date: 07/20/2015
f1_keywords:
- vbrID460
ms.assetid: 71a4a045-65bb-417d-b3bd-99a9fa3c53f6
ms.openlocfilehash: 15bc530d1030a8c4d720321ea249fdd7fb6cd8b6
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/28/2019
ms.locfileid: "64623101"
---
# <a name="clipboard-format-is-not-valid"></a><span data-ttu-id="bbd54-102">Недопустимый формат буфера обмена</span><span class="sxs-lookup"><span data-stu-id="bbd54-102">Clipboard format is not valid</span></span>
<span data-ttu-id="bbd54-103">Указанный формат буфера обмена не совместим с выполняемый метод.</span><span class="sxs-lookup"><span data-stu-id="bbd54-103">The specified Clipboard format is incompatible with the method being executed.</span></span> <span data-ttu-id="bbd54-104">Среди возможных причин этой ошибки:</span><span class="sxs-lookup"><span data-stu-id="bbd54-104">Among the possible causes for this error are:</span></span>  
  
- <span data-ttu-id="bbd54-105">Использование буфера обмена `GetText` или `SetText` метод с формат буфера обмена, отличных от `vbCFText` или `vbCFLink`.</span><span class="sxs-lookup"><span data-stu-id="bbd54-105">Using the Clipboard's `GetText` or `SetText` method with a Clipboard format other than `vbCFText` or `vbCFLink`.</span></span>  
  
- <span data-ttu-id="bbd54-106">Использование буфера обмена `GetData` или `SetData` метод с формат буфера обмена, отличных от `vbCFBitmap`, `vbCFDIB`, или `vbCFMetafile`.</span><span class="sxs-lookup"><span data-stu-id="bbd54-106">Using the Clipboard's `GetData` or `SetData` method with a Clipboard format other than `vbCFBitmap`, `vbCFDIB`, or `vbCFMetafile`.</span></span>  
  
- <span data-ttu-id="bbd54-107">С помощью `GetData` или `SetData` методы `DataObject` с формат буфера обмена в диапазоне, зарезервированной с помощью Microsoft Windows для зарегистрированных форматов (& HC000 - & HFFFF), при этом формат буфера обмена не был зарегистрирован с помощью Microsoft Windows .</span><span class="sxs-lookup"><span data-stu-id="bbd54-107">Using the `GetData` or `SetData` methods of a `DataObject` with a Clipboard format in the range reserved by Microsoft Windows for registered formats (&HC000-&HFFFF), when that Clipboard format has not been registered with Microsoft Windows.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="bbd54-108">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="bbd54-108">To correct this error</span></span>  
  
- <span data-ttu-id="bbd54-109">Удалите недопустимый формат и укажите допустимый.</span><span class="sxs-lookup"><span data-stu-id="bbd54-109">Remove the invalid format and specify a valid one.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bbd54-110">См. также</span><span class="sxs-lookup"><span data-stu-id="bbd54-110">See also</span></span>

- [<span data-ttu-id="bbd54-111">Буфер обмена. Добавление других форматов</span><span class="sxs-lookup"><span data-stu-id="bbd54-111">Clipboard: Adding Other Formats</span></span>](/cpp/mfc/clipboard-adding-other-formats)
