---
title: Интерфейс ISymUnmanagedBinder2
ms.date: 03/30/2017
api_name:
- ISymUnmanagedBinder2
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedBinder2 Interface
helpviewer_keywords:
- ISymUnmanagedBinder2 interface [.NET Framework debugging]
ms.assetid: 7a59f405-73e8-4434-8bcc-a9dc45ea08e6
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 52b0f6b9d3e0ea3d6fe5f14badb8401b1a0c2c63
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/27/2018
ms.locfileid: "50187496"
---
# <a name="isymunmanagedbinder2-interface"></a><span data-ttu-id="91a49-102">Интерфейс ISymUnmanagedBinder2</span><span class="sxs-lookup"><span data-stu-id="91a49-102">ISymUnmanagedBinder2 Interface</span></span>
<span data-ttu-id="91a49-103">Представляет модуль привязки символов для неуправляемого кода и расширяет [ISymUnmanagedBinder](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder-interface.md) интерфейс.</span><span class="sxs-lookup"><span data-stu-id="91a49-103">Represents a symbol binder for unmanaged code, and extends the [ISymUnmanagedBinder](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder-interface.md) interface.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="91a49-104">Он представляет угрозу безопасности, чтобы открыть файл базы данных (PDB) программы из ненадежного источника.</span><span class="sxs-lookup"><span data-stu-id="91a49-104">It is a security risk to open a program database (PDB) file from an untrusted source.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="91a49-105">Методы</span><span class="sxs-lookup"><span data-stu-id="91a49-105">Methods</span></span>  
  
|<span data-ttu-id="91a49-106">Метод</span><span class="sxs-lookup"><span data-stu-id="91a49-106">Method</span></span>|<span data-ttu-id="91a49-107">Описание</span><span class="sxs-lookup"><span data-stu-id="91a49-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="91a49-108">Метод GetReaderForFile2</span><span class="sxs-lookup"><span data-stu-id="91a49-108">GetReaderForFile2 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder2-getreaderforfile2-method.md)|<span data-ttu-id="91a49-109">Данный интерфейс метаданных и имя файла, возвращает правильный [ISymUnmanagedReader](isymunmanagedreader-interface.md) интерфейс, который будет считывать символы отладки, связанные с модулем.</span><span class="sxs-lookup"><span data-stu-id="91a49-109">Given a metadata interface and a file name, returns the correct [ISymUnmanagedReader](isymunmanagedreader-interface.md) interface that will read the debugging symbols associated with the module.</span></span> <span data-ttu-id="91a49-110">Предоставляет расширенный поиск чем [ISymUnmanagedBinder::GetReaderForFile](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder-getreaderforfile-method.md) метод.</span><span class="sxs-lookup"><span data-stu-id="91a49-110">Provides a more extensive search than the [ISymUnmanagedBinder::GetReaderForFile](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder-getreaderforfile-method.md) method.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="91a49-111">Требования</span><span class="sxs-lookup"><span data-stu-id="91a49-111">Requirements</span></span>  
 <span data-ttu-id="91a49-112">**Заголовок:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="91a49-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="91a49-113">См. также</span><span class="sxs-lookup"><span data-stu-id="91a49-113">See Also</span></span>  
 [<span data-ttu-id="91a49-114">Интерфейсы хранилища символов диагностики</span><span class="sxs-lookup"><span data-stu-id="91a49-114">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)  
 [<span data-ttu-id="91a49-115">Интерфейс ISymUnmanagedBinder</span><span class="sxs-lookup"><span data-stu-id="91a49-115">ISymUnmanagedBinder Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder-interface.md)  
 [<span data-ttu-id="91a49-116">Интерфейс ISymUnmanagedBinder3</span><span class="sxs-lookup"><span data-stu-id="91a49-116">ISymUnmanagedBinder3 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder3-interface.md)
