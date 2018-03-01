---
title: "Интерфейс ISymENCUnmanagedMethod"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
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
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: f7cc1cea74cc632c65c7e3c2aee408e2f9e864d1
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="isymencunmanagedmethod-interface"></a><span data-ttu-id="f6d73-102">Интерфейс ISymENCUnmanagedMethod</span><span class="sxs-lookup"><span data-stu-id="f6d73-102">ISymENCUnmanagedMethod Interface</span></span>
<span data-ttu-id="f6d73-103">Предоставляет сведения для "Изменить и продолжить".</span><span class="sxs-lookup"><span data-stu-id="f6d73-103">Provides information for the Edit and Continue feature.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="f6d73-104">Методы</span><span class="sxs-lookup"><span data-stu-id="f6d73-104">Methods</span></span>  
  
|<span data-ttu-id="f6d73-105">Метод</span><span class="sxs-lookup"><span data-stu-id="f6d73-105">Method</span></span>|<span data-ttu-id="f6d73-106">Описание:</span><span class="sxs-lookup"><span data-stu-id="f6d73-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="f6d73-107">Метод GetDocumentsForMethod</span><span class="sxs-lookup"><span data-stu-id="f6d73-107">GetDocumentsForMethod Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymencunmanagedmethod-getdocumentsformethod-method.md)|<span data-ttu-id="f6d73-108">Возвращает документы, которые этот метод имеет строки.</span><span class="sxs-lookup"><span data-stu-id="f6d73-108">Gets the documents that this method has lines in.</span></span>|  
|[<span data-ttu-id="f6d73-109">Метод GetDocumentsForMethodCount</span><span class="sxs-lookup"><span data-stu-id="f6d73-109">GetDocumentsForMethodCount Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymencunmanagedmethod-getdocumentsformethodcount-method.md)|<span data-ttu-id="f6d73-110">Возвращает количество документов, этот метод имеет строки.</span><span class="sxs-lookup"><span data-stu-id="f6d73-110">Gets the number of documents that this method has lines in.</span></span>|  
|[<span data-ttu-id="f6d73-111">Метод GetFileNameFromOffset</span><span class="sxs-lookup"><span data-stu-id="f6d73-111">GetFileNameFromOffset Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymencunmanagedmethod-getfilenamefromoffset-method.md)|<span data-ttu-id="f6d73-112">Получает имя файла для строки, связанной со смещением.</span><span class="sxs-lookup"><span data-stu-id="f6d73-112">Gets the file name for the line associated with an offset.</span></span>|  
|[<span data-ttu-id="f6d73-113">Метод GetLineFromOffset</span><span class="sxs-lookup"><span data-stu-id="f6d73-113">GetLineFromOffset Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymencunmanagedmethod-getlinefromoffset-method.md)|<span data-ttu-id="f6d73-114">Возвращает сведения о строке, связанной со смещением.</span><span class="sxs-lookup"><span data-stu-id="f6d73-114">Gets the line information associated with an offset.</span></span>|  
|[<span data-ttu-id="f6d73-115">Метод GetSourceExtentInDocument</span><span class="sxs-lookup"><span data-stu-id="f6d73-115">GetSourceExtentInDocument Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymencunmanagedmethod-getsourceextentindocument-method.md)|<span data-ttu-id="f6d73-116">Возвращает наименьшую начальную или наибольшую конечную строку метода в определенном документе.</span><span class="sxs-lookup"><span data-stu-id="f6d73-116">Gets the smallest start line and largest end line for the method in a specific document.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="f6d73-117">Требования</span><span class="sxs-lookup"><span data-stu-id="f6d73-117">Requirements</span></span>  
 <span data-ttu-id="f6d73-118">**Заголовок:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="f6d73-118">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f6d73-119">См. также</span><span class="sxs-lookup"><span data-stu-id="f6d73-119">See Also</span></span>  
 [<span data-ttu-id="f6d73-120">Интерфейсы хранилища символов диагностики</span><span class="sxs-lookup"><span data-stu-id="f6d73-120">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
