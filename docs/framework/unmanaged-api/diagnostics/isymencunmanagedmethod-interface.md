---
title: Интерфейс ISymENCUnmanagedMethod
ms.date: 03/30/2017
api_name:
- ISymENCUnmanagedMethod
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymENCUnmanagedMethod
helpviewer_keywords:
- ISymENCUnmanagedMethod interface [.NET Framework debugging]
ms.assetid: faebf594-67d5-4abf-b9c1-547fd3a1ff87
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 4474269688094ea6c81b06659727acfb9c2ad6c3
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59095715"
---
# <a name="isymencunmanagedmethod-interface"></a><span data-ttu-id="f8494-102">Интерфейс ISymENCUnmanagedMethod</span><span class="sxs-lookup"><span data-stu-id="f8494-102">ISymENCUnmanagedMethod Interface</span></span>
<span data-ttu-id="f8494-103">Предоставляет сведения для "Изменить и продолжить".</span><span class="sxs-lookup"><span data-stu-id="f8494-103">Provides information for the Edit and Continue feature.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="f8494-104">Методы</span><span class="sxs-lookup"><span data-stu-id="f8494-104">Methods</span></span>  
  
|<span data-ttu-id="f8494-105">Метод</span><span class="sxs-lookup"><span data-stu-id="f8494-105">Method</span></span>|<span data-ttu-id="f8494-106">Описание</span><span class="sxs-lookup"><span data-stu-id="f8494-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="f8494-107">Метод GetDocumentsForMethod</span><span class="sxs-lookup"><span data-stu-id="f8494-107">GetDocumentsForMethod Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymencunmanagedmethod-getdocumentsformethod-method.md)|<span data-ttu-id="f8494-108">Возвращает документы, которые этот метод имеет строки.</span><span class="sxs-lookup"><span data-stu-id="f8494-108">Gets the documents that this method has lines in.</span></span>|  
|[<span data-ttu-id="f8494-109">Метод GetDocumentsForMethodCount</span><span class="sxs-lookup"><span data-stu-id="f8494-109">GetDocumentsForMethodCount Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymencunmanagedmethod-getdocumentsformethodcount-method.md)|<span data-ttu-id="f8494-110">Возвращает количество документов, этот метод имеет строки.</span><span class="sxs-lookup"><span data-stu-id="f8494-110">Gets the number of documents that this method has lines in.</span></span>|  
|[<span data-ttu-id="f8494-111">Метод GetFileNameFromOffset</span><span class="sxs-lookup"><span data-stu-id="f8494-111">GetFileNameFromOffset Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymencunmanagedmethod-getfilenamefromoffset-method.md)|<span data-ttu-id="f8494-112">Получает имя файла для строки, связанной со смещением.</span><span class="sxs-lookup"><span data-stu-id="f8494-112">Gets the file name for the line associated with an offset.</span></span>|  
|[<span data-ttu-id="f8494-113">Метод GetLineFromOffset</span><span class="sxs-lookup"><span data-stu-id="f8494-113">GetLineFromOffset Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymencunmanagedmethod-getlinefromoffset-method.md)|<span data-ttu-id="f8494-114">Получает сведения о строке, связанной со смещением.</span><span class="sxs-lookup"><span data-stu-id="f8494-114">Gets the line information associated with an offset.</span></span>|  
|[<span data-ttu-id="f8494-115">Метод GetSourceExtentInDocument</span><span class="sxs-lookup"><span data-stu-id="f8494-115">GetSourceExtentInDocument Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymencunmanagedmethod-getsourceextentindocument-method.md)|<span data-ttu-id="f8494-116">Получает наименьшую начальную строку и наибольшую конечную строку метода в определенном документе.</span><span class="sxs-lookup"><span data-stu-id="f8494-116">Gets the smallest start line and largest end line for the method in a specific document.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="f8494-117">Требования</span><span class="sxs-lookup"><span data-stu-id="f8494-117">Requirements</span></span>  
 <span data-ttu-id="f8494-118">**Заголовок.** CorSym.idl CorSym.h</span><span class="sxs-lookup"><span data-stu-id="f8494-118">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f8494-119">См. также</span><span class="sxs-lookup"><span data-stu-id="f8494-119">See also</span></span>

- [<span data-ttu-id="f8494-120">Интерфейсы хранилища символов диагностики</span><span class="sxs-lookup"><span data-stu-id="f8494-120">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
