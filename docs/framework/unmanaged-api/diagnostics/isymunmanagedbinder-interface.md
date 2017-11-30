---
title: "Интерфейс ISymUnmanagedBinder"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedBinder
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedBinder
helpviewer_keywords: ISymUnmanagedBinder interface [.NET Framework debugging]
ms.assetid: b22fbe19-b30f-4696-8175-e6b91da9edab
topic_type: apiref
caps.latest.revision: "8"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 00b0b5ee330a606ae7417185a804f3d37ab6664a
ms.sourcegitcommit: 5177d6ae2e9baf026f07ee0631556700a5a193f7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/28/2017
---
# <a name="isymunmanagedbinder-interface"></a><span data-ttu-id="bd694-102">Интерфейс ISymUnmanagedBinder</span><span class="sxs-lookup"><span data-stu-id="bd694-102">ISymUnmanagedBinder Interface</span></span>
<span data-ttu-id="bd694-103">Представляет модуль привязки символов для неуправляемого кода.</span><span class="sxs-lookup"><span data-stu-id="bd694-103">Represents a symbol binder for unmanaged code.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="bd694-104">Он представляет угрозу безопасности, чтобы открыть файл программы (PDB) из ненадежного источника.</span><span class="sxs-lookup"><span data-stu-id="bd694-104">It is a security risk to open a program database (PDB) file from an untrusted source.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="bd694-105">Методы</span><span class="sxs-lookup"><span data-stu-id="bd694-105">Methods</span></span>  
  
|<span data-ttu-id="bd694-106">Метод</span><span class="sxs-lookup"><span data-stu-id="bd694-106">Method</span></span>|<span data-ttu-id="bd694-107">Описание</span><span class="sxs-lookup"><span data-stu-id="bd694-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="bd694-108">Метод GetReaderForFile</span><span class="sxs-lookup"><span data-stu-id="bd694-108">GetReaderForFile Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder-getreaderforfile-method.md)|<span data-ttu-id="bd694-109">Данный интерфейс метаданных и имя файла, возвращает правильную [ISymUnmanagedReader](isymunmanagedreader-interface.md) структуру, которая будет считывать символы отладки, связанные с модулем.</span><span class="sxs-lookup"><span data-stu-id="bd694-109">Given a metadata interface and a file name, returns the correct [ISymUnmanagedReader](isymunmanagedreader-interface.md) structure that will read the debugging symbols associated with the module.</span></span>|  
|[<span data-ttu-id="bd694-110">Метод GetReaderFromStream</span><span class="sxs-lookup"><span data-stu-id="bd694-110">GetReaderFromStream Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder-getreaderfromstream-method.md)|<span data-ttu-id="bd694-111">Данный интерфейс метаданных и поток, содержащий хранилище символов, возвращает правильную [ISymUnmanagedReader](isymunmanagedreader-interface.md) структуру, которая будет считывать отладочных символов из данного хранилища символов.</span><span class="sxs-lookup"><span data-stu-id="bd694-111">Given a metadata interface and a stream that contains the symbol store, returns the correct [ISymUnmanagedReader](isymunmanagedreader-interface.md) structure that will read the debugging symbols from the given symbol store.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="bd694-112">Требования</span><span class="sxs-lookup"><span data-stu-id="bd694-112">Requirements</span></span>  
 <span data-ttu-id="bd694-113">**Заголовок:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="bd694-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bd694-114">См. также</span><span class="sxs-lookup"><span data-stu-id="bd694-114">See Also</span></span>  
 [<span data-ttu-id="bd694-115">Интерфейсы хранилища символов диагностики</span><span class="sxs-lookup"><span data-stu-id="bd694-115">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)  
 [<span data-ttu-id="bd694-116">Интерфейс ISymUnmanagedBinder2</span><span class="sxs-lookup"><span data-stu-id="bd694-116">ISymUnmanagedBinder2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder2-interface.md)  
 [<span data-ttu-id="bd694-117">Интерфейс ISymUnmanagedBinder3</span><span class="sxs-lookup"><span data-stu-id="bd694-117">ISymUnmanagedBinder3 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder3-interface.md)
