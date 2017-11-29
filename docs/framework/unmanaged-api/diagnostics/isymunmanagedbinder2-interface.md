---
title: "Интерфейс ISymUnmanagedBinder2"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedBinder2
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedBinder2 Interface
helpviewer_keywords: ISymUnmanagedBinder2 interface [.NET Framework debugging]
ms.assetid: 7a59f405-73e8-4434-8bcc-a9dc45ea08e6
topic_type: apiref
caps.latest.revision: "8"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: c276f0abedf4ccab92770af649a8dd0afb6d39d2
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="isymunmanagedbinder2-interface"></a><span data-ttu-id="c9908-102">Интерфейс ISymUnmanagedBinder2</span><span class="sxs-lookup"><span data-stu-id="c9908-102">ISymUnmanagedBinder2 Interface</span></span>
<span data-ttu-id="c9908-103">Представляет модуль привязки символов для неуправляемого кода и расширяет возможности [ISymUnmanagedBinder](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder-interface.md) интерфейса.</span><span class="sxs-lookup"><span data-stu-id="c9908-103">Represents a symbol binder for unmanaged code, and extends the [ISymUnmanagedBinder](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder-interface.md) interface.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="c9908-104">Он представляет угрозу безопасности, чтобы открыть файл программы (PDB) из ненадежного источника.</span><span class="sxs-lookup"><span data-stu-id="c9908-104">It is a security risk to open a program database (PDB) file from an untrusted source.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="c9908-105">Методы</span><span class="sxs-lookup"><span data-stu-id="c9908-105">Methods</span></span>  
  
|<span data-ttu-id="c9908-106">Метод</span><span class="sxs-lookup"><span data-stu-id="c9908-106">Method</span></span>|<span data-ttu-id="c9908-107">Описание</span><span class="sxs-lookup"><span data-stu-id="c9908-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="c9908-108">Метод GetReaderForFile2</span><span class="sxs-lookup"><span data-stu-id="c9908-108">GetReaderForFile2 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder2-getreaderforfile2-method.md)|<span data-ttu-id="c9908-109">Данный интерфейс метаданных и имя файла, возвращает правильную <<!--zz xref:ISymUnmanagedReader --> `ISymUnmanagedReader`> интерфейс, который будет считывать символы отладки, связанные с модулем.</span><span class="sxs-lookup"><span data-stu-id="c9908-109">Given a metadata interface and a file name, returns the correct <<!--zz xref:ISymUnmanagedReader --> `ISymUnmanagedReader`> interface that will read the debugging symbols associated with the module.</span></span> <span data-ttu-id="c9908-110">Предоставляет расширенный поиск чем [ISymUnmanagedBinder::GetReaderForFile](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder-getreaderforfile-method.md) метод.</span><span class="sxs-lookup"><span data-stu-id="c9908-110">Provides a more extensive search than the [ISymUnmanagedBinder::GetReaderForFile](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder-getreaderforfile-method.md) method.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="c9908-111">Требования</span><span class="sxs-lookup"><span data-stu-id="c9908-111">Requirements</span></span>  
 <span data-ttu-id="c9908-112">**Заголовок:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="c9908-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c9908-113">См. также</span><span class="sxs-lookup"><span data-stu-id="c9908-113">See Also</span></span>  
 [<span data-ttu-id="c9908-114">Интерфейсы хранилища символов диагностики</span><span class="sxs-lookup"><span data-stu-id="c9908-114">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)  
 [<span data-ttu-id="c9908-115">Интерфейс ISymUnmanagedBinder</span><span class="sxs-lookup"><span data-stu-id="c9908-115">ISymUnmanagedBinder Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder-interface.md)  
 [<span data-ttu-id="c9908-116">Интерфейс ISymUnmanagedBinder3</span><span class="sxs-lookup"><span data-stu-id="c9908-116">ISymUnmanagedBinder3 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder3-interface.md)
