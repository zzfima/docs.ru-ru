---
title: Недопустимый формат буфера обмена
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbrID460
ms.assetid: 71a4a045-65bb-417d-b3bd-99a9fa3c53f6
caps.latest.revision: 10
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 0e7adc417d962de35272319d7dc976b237c7e2b6
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="clipboard-format-is-not-valid"></a><span data-ttu-id="d4d38-102">Недопустимый формат буфера обмена</span><span class="sxs-lookup"><span data-stu-id="d4d38-102">Clipboard format is not valid</span></span>
<span data-ttu-id="d4d38-103">Указанный формат буфера обмена не совместим с выполняемый метод.</span><span class="sxs-lookup"><span data-stu-id="d4d38-103">The specified Clipboard format is incompatible with the method being executed.</span></span> <span data-ttu-id="d4d38-104">Среди возможных причин этой ошибки являются:</span><span class="sxs-lookup"><span data-stu-id="d4d38-104">Among the possible causes for this error are:</span></span>  
  
-   <span data-ttu-id="d4d38-105">Использование буфера обмена `GetText` или `SetText` метод с форматом буфера обмена, отличным от `vbCFText` или `vbCFLink`.</span><span class="sxs-lookup"><span data-stu-id="d4d38-105">Using the Clipboard's `GetText` or `SetText` method with a Clipboard format other than `vbCFText` or `vbCFLink`.</span></span>  
  
-   <span data-ttu-id="d4d38-106">Использование буфера обмена `GetData` или `SetData` метод с форматом буфера обмена, отличным от `vbCFBitmap`, `vbCFDIB`, или `vbCFMetafile`.</span><span class="sxs-lookup"><span data-stu-id="d4d38-106">Using the Clipboard's `GetData` or `SetData` method with a Clipboard format other than `vbCFBitmap`, `vbCFDIB`, or `vbCFMetafile`.</span></span>  
  
-   <span data-ttu-id="d4d38-107">С помощью `DataObject``GetData` метода или `SetData` метод с форматом буфера обмена в диапазоне, зарезервированном Microsoft Windows для зарегистрированных форматов (& HC000 - & HFFFF), при этом формат буфера обмена не был зарегистрирован с Microsoft Windows.</span><span class="sxs-lookup"><span data-stu-id="d4d38-107">Using the `DataObject``GetData` method or `SetData` method with a Clipboard format in the range reserved by Microsoft Windows for registered formats (&HC000-&HFFFF), when that Clipboard format has not been registered with Microsoft Windows.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="d4d38-108">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="d4d38-108">To correct this error</span></span>  
  
-   <span data-ttu-id="d4d38-109">Удалите недопустимый формат и укажите допустимый.</span><span class="sxs-lookup"><span data-stu-id="d4d38-109">Remove the invalid format and specify a valid one.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d4d38-110">См. также</span><span class="sxs-lookup"><span data-stu-id="d4d38-110">See Also</span></span>  
 [<span data-ttu-id="d4d38-111">Буфер обмена. Добавление других форматов</span><span class="sxs-lookup"><span data-stu-id="d4d38-111">Clipboard: Adding Other Formats</span></span>](/cpp/mfc/clipboard-adding-other-formats)
