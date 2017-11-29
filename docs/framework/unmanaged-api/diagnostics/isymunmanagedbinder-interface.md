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
ms.openlocfilehash: 5061ce28c4a09f445267c99420bf1942d99076bf
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="isymunmanagedbinder-interface"></a><span data-ttu-id="792fd-102">Интерфейс ISymUnmanagedBinder</span><span class="sxs-lookup"><span data-stu-id="792fd-102">ISymUnmanagedBinder Interface</span></span>
<span data-ttu-id="792fd-103">Представляет модуль привязки символов для неуправляемого кода.</span><span class="sxs-lookup"><span data-stu-id="792fd-103">Represents a symbol binder for unmanaged code.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="792fd-104">Он представляет угрозу безопасности, чтобы открыть файл программы (PDB) из ненадежного источника.</span><span class="sxs-lookup"><span data-stu-id="792fd-104">It is a security risk to open a program database (PDB) file from an untrusted source.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="792fd-105">Методы</span><span class="sxs-lookup"><span data-stu-id="792fd-105">Methods</span></span>  
  
|<span data-ttu-id="792fd-106">Метод</span><span class="sxs-lookup"><span data-stu-id="792fd-106">Method</span></span>|<span data-ttu-id="792fd-107">Описание</span><span class="sxs-lookup"><span data-stu-id="792fd-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="792fd-108">Метод GetReaderForFile</span><span class="sxs-lookup"><span data-stu-id="792fd-108">GetReaderForFile Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder-getreaderforfile-method.md)|<span data-ttu-id="792fd-109">Данный интерфейс метаданных и имя файла, возвращает правильную <<!--zz xref:ISymUnmanagedReader --> `ISymUnmanagedReader`> структуру, которая будет считывать символы отладки, связанные с модулем.</span><span class="sxs-lookup"><span data-stu-id="792fd-109">Given a metadata interface and a file name, returns the correct <<!--zz xref:ISymUnmanagedReader --> `ISymUnmanagedReader`> structure that will read the debugging symbols associated with the module.</span></span>|  
|[<span data-ttu-id="792fd-110">Метод GetReaderFromStream</span><span class="sxs-lookup"><span data-stu-id="792fd-110">GetReaderFromStream Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder-getreaderfromstream-method.md)|<span data-ttu-id="792fd-111">Данный интерфейс метаданных и поток, содержащий хранилище символов, возвращает правильную <<!--zz xref:ISymUnmanagedReader --> `ISymUnmanagedReader`> структуру, которая будет считывать отладочных символов из данного хранилища символов.</span><span class="sxs-lookup"><span data-stu-id="792fd-111">Given a metadata interface and a stream that contains the symbol store, returns the correct <<!--zz xref:ISymUnmanagedReader --> `ISymUnmanagedReader`> structure that will read the debugging symbols from the given symbol store.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="792fd-112">Требования</span><span class="sxs-lookup"><span data-stu-id="792fd-112">Requirements</span></span>  
 <span data-ttu-id="792fd-113">**Заголовок:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="792fd-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="792fd-114">См. также</span><span class="sxs-lookup"><span data-stu-id="792fd-114">See Also</span></span>  
 [<span data-ttu-id="792fd-115">Интерфейсы хранилища символов диагностики</span><span class="sxs-lookup"><span data-stu-id="792fd-115">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)  
 [<span data-ttu-id="792fd-116">Интерфейс ISymUnmanagedBinder2</span><span class="sxs-lookup"><span data-stu-id="792fd-116">ISymUnmanagedBinder2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder2-interface.md)  
 [<span data-ttu-id="792fd-117">Интерфейс ISymUnmanagedBinder3</span><span class="sxs-lookup"><span data-stu-id="792fd-117">ISymUnmanagedBinder3 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder3-interface.md)
