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
ms.openlocfilehash: c9fbb8364fb967e739eb9807b26cbc65f0ebec1d
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69944196"
---
# <a name="isymunmanagedbinder2-interface"></a><span data-ttu-id="f0fba-102">Интерфейс ISymUnmanagedBinder2</span><span class="sxs-lookup"><span data-stu-id="f0fba-102">ISymUnmanagedBinder2 Interface</span></span>
<span data-ttu-id="f0fba-103">Представляет связыватель символов для неуправляемого кода и расширяет интерфейс [ISymUnmanagedBinder](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="f0fba-103">Represents a symbol binder for unmanaged code, and extends the [ISymUnmanagedBinder](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder-interface.md) interface.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="f0fba-104">При открытии файла базы данных программы (PDB) из ненадежного источника возникает угроза безопасности.</span><span class="sxs-lookup"><span data-stu-id="f0fba-104">It is a security risk to open a program database (PDB) file from an untrusted source.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="f0fba-105">Методы</span><span class="sxs-lookup"><span data-stu-id="f0fba-105">Methods</span></span>  
  
|<span data-ttu-id="f0fba-106">Метод</span><span class="sxs-lookup"><span data-stu-id="f0fba-106">Method</span></span>|<span data-ttu-id="f0fba-107">Описание</span><span class="sxs-lookup"><span data-stu-id="f0fba-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="f0fba-108">Метод GetReaderForFile2</span><span class="sxs-lookup"><span data-stu-id="f0fba-108">GetReaderForFile2 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder2-getreaderforfile2-method.md)|<span data-ttu-id="f0fba-109">При наличии интерфейса метаданных и имени файла возвращает правильный интерфейс [ISymUnmanagedReader](isymunmanagedreader-interface.md) , который будет считывать символы отладки, связанные с модулем.</span><span class="sxs-lookup"><span data-stu-id="f0fba-109">Given a metadata interface and a file name, returns the correct [ISymUnmanagedReader](isymunmanagedreader-interface.md) interface that will read the debugging symbols associated with the module.</span></span> <span data-ttu-id="f0fba-110">Предоставляет более широкие возможности поиска, чем метод [ISymUnmanagedBinder:: getreaderforfile:](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder-getreaderforfile-method.md) .</span><span class="sxs-lookup"><span data-stu-id="f0fba-110">Provides a more extensive search than the [ISymUnmanagedBinder::GetReaderForFile](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder-getreaderforfile-method.md) method.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="f0fba-111">Требования</span><span class="sxs-lookup"><span data-stu-id="f0fba-111">Requirements</span></span>  
 <span data-ttu-id="f0fba-112">**Заголовок.** Корсим. idl, Корсим. h</span><span class="sxs-lookup"><span data-stu-id="f0fba-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f0fba-113">См. также</span><span class="sxs-lookup"><span data-stu-id="f0fba-113">See also</span></span>

- [<span data-ttu-id="f0fba-114">Интерфейсы хранилища символов диагностики</span><span class="sxs-lookup"><span data-stu-id="f0fba-114">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
- [<span data-ttu-id="f0fba-115">Интерфейс ISymUnmanagedBinder</span><span class="sxs-lookup"><span data-stu-id="f0fba-115">ISymUnmanagedBinder Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder-interface.md)
- [<span data-ttu-id="f0fba-116">Интерфейс ISymUnmanagedBinder3</span><span class="sxs-lookup"><span data-stu-id="f0fba-116">ISymUnmanagedBinder3 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder3-interface.md)
