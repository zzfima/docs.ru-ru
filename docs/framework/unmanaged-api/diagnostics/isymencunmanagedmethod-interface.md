---
title: "Интерфейс ISymENCUnmanagedMethod"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymENCUnmanagedMethod
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymENCUnmanagedMethod
helpviewer_keywords: ISymENCUnmanagedMethod interface [.NET Framework debugging]
ms.assetid: faebf594-67d5-4abf-b9c1-547fd3a1ff87
topic_type: apiref
caps.latest.revision: "7"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 68929dc30b029133c73f18c3749f39f014359c0d
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="isymencunmanagedmethod-interface"></a><span data-ttu-id="99670-102">Интерфейс ISymENCUnmanagedMethod</span><span class="sxs-lookup"><span data-stu-id="99670-102">ISymENCUnmanagedMethod Interface</span></span>
<span data-ttu-id="99670-103">Предоставляет сведения для "Изменить и продолжить".</span><span class="sxs-lookup"><span data-stu-id="99670-103">Provides information for the Edit and Continue feature.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="99670-104">Методы</span><span class="sxs-lookup"><span data-stu-id="99670-104">Methods</span></span>  
  
|<span data-ttu-id="99670-105">Метод</span><span class="sxs-lookup"><span data-stu-id="99670-105">Method</span></span>|<span data-ttu-id="99670-106">Описание</span><span class="sxs-lookup"><span data-stu-id="99670-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="99670-107">Метод GetDocumentsForMethod</span><span class="sxs-lookup"><span data-stu-id="99670-107">GetDocumentsForMethod Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymencunmanagedmethod-getdocumentsformethod-method.md)|<span data-ttu-id="99670-108">Возвращает документы, которые этот метод имеет строки.</span><span class="sxs-lookup"><span data-stu-id="99670-108">Gets the documents that this method has lines in.</span></span>|  
|[<span data-ttu-id="99670-109">Метод GetDocumentsForMethodCount</span><span class="sxs-lookup"><span data-stu-id="99670-109">GetDocumentsForMethodCount Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymencunmanagedmethod-getdocumentsformethodcount-method.md)|<span data-ttu-id="99670-110">Возвращает количество документов, этот метод имеет строки.</span><span class="sxs-lookup"><span data-stu-id="99670-110">Gets the number of documents that this method has lines in.</span></span>|  
|[<span data-ttu-id="99670-111">Метод GetFileNameFromOffset</span><span class="sxs-lookup"><span data-stu-id="99670-111">GetFileNameFromOffset Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymencunmanagedmethod-getfilenamefromoffset-method.md)|<span data-ttu-id="99670-112">Получает имя файла для строки, связанной со смещением.</span><span class="sxs-lookup"><span data-stu-id="99670-112">Gets the file name for the line associated with an offset.</span></span>|  
|[<span data-ttu-id="99670-113">Метод GetLineFromOffset</span><span class="sxs-lookup"><span data-stu-id="99670-113">GetLineFromOffset Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymencunmanagedmethod-getlinefromoffset-method.md)|<span data-ttu-id="99670-114">Возвращает сведения о строке, связанной со смещением.</span><span class="sxs-lookup"><span data-stu-id="99670-114">Gets the line information associated with an offset.</span></span>|  
|[<span data-ttu-id="99670-115">Метод GetSourceExtentInDocument</span><span class="sxs-lookup"><span data-stu-id="99670-115">GetSourceExtentInDocument Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymencunmanagedmethod-getsourceextentindocument-method.md)|<span data-ttu-id="99670-116">Возвращает наименьшую начальную или наибольшую конечную строку метода в определенном документе.</span><span class="sxs-lookup"><span data-stu-id="99670-116">Gets the smallest start line and largest end line for the method in a specific document.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="99670-117">Требования</span><span class="sxs-lookup"><span data-stu-id="99670-117">Requirements</span></span>  
 <span data-ttu-id="99670-118">**Заголовок:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="99670-118">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="99670-119">См. также</span><span class="sxs-lookup"><span data-stu-id="99670-119">See Also</span></span>  
 [<span data-ttu-id="99670-120">Интерфейсы хранилища символов диагностики</span><span class="sxs-lookup"><span data-stu-id="99670-120">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
