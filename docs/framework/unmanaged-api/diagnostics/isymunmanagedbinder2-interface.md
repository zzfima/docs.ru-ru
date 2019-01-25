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
ms.openlocfilehash: 49949989a48be13bcb70b27e47407d907b284670
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54494958"
---
# <a name="isymunmanagedbinder2-interface"></a><span data-ttu-id="ed7f6-102">Интерфейс ISymUnmanagedBinder2</span><span class="sxs-lookup"><span data-stu-id="ed7f6-102">ISymUnmanagedBinder2 Interface</span></span>
<span data-ttu-id="ed7f6-103">Представляет модуль привязки символов для неуправляемого кода и расширяет [ISymUnmanagedBinder](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder-interface.md) интерфейс.</span><span class="sxs-lookup"><span data-stu-id="ed7f6-103">Represents a symbol binder for unmanaged code, and extends the [ISymUnmanagedBinder](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder-interface.md) interface.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="ed7f6-104">Он представляет угрозу безопасности, чтобы открыть файл базы данных (PDB) программы из ненадежного источника.</span><span class="sxs-lookup"><span data-stu-id="ed7f6-104">It is a security risk to open a program database (PDB) file from an untrusted source.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="ed7f6-105">Методы</span><span class="sxs-lookup"><span data-stu-id="ed7f6-105">Methods</span></span>  
  
|<span data-ttu-id="ed7f6-106">Метод</span><span class="sxs-lookup"><span data-stu-id="ed7f6-106">Method</span></span>|<span data-ttu-id="ed7f6-107">Описание:</span><span class="sxs-lookup"><span data-stu-id="ed7f6-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="ed7f6-108">Метод GetReaderForFile2</span><span class="sxs-lookup"><span data-stu-id="ed7f6-108">GetReaderForFile2 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder2-getreaderforfile2-method.md)|<span data-ttu-id="ed7f6-109">Данный интерфейс метаданных и имя файла, возвращает правильный [ISymUnmanagedReader](isymunmanagedreader-interface.md) интерфейс, который будет считывать символы отладки, связанные с модулем.</span><span class="sxs-lookup"><span data-stu-id="ed7f6-109">Given a metadata interface and a file name, returns the correct [ISymUnmanagedReader](isymunmanagedreader-interface.md) interface that will read the debugging symbols associated with the module.</span></span> <span data-ttu-id="ed7f6-110">Предоставляет расширенный поиск чем [ISymUnmanagedBinder::GetReaderForFile](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder-getreaderforfile-method.md) метод.</span><span class="sxs-lookup"><span data-stu-id="ed7f6-110">Provides a more extensive search than the [ISymUnmanagedBinder::GetReaderForFile](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder-getreaderforfile-method.md) method.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="ed7f6-111">Требования</span><span class="sxs-lookup"><span data-stu-id="ed7f6-111">Requirements</span></span>  
 <span data-ttu-id="ed7f6-112">**Заголовок.** CorSym.idl CorSym.h</span><span class="sxs-lookup"><span data-stu-id="ed7f6-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ed7f6-113">См. также</span><span class="sxs-lookup"><span data-stu-id="ed7f6-113">See also</span></span>
- [<span data-ttu-id="ed7f6-114">Интерфейсы хранилища символов диагностики</span><span class="sxs-lookup"><span data-stu-id="ed7f6-114">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
- [<span data-ttu-id="ed7f6-115">Интерфейс ISymUnmanagedBinder</span><span class="sxs-lookup"><span data-stu-id="ed7f6-115">ISymUnmanagedBinder Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder-interface.md)
- [<span data-ttu-id="ed7f6-116">Интерфейс ISymUnmanagedBinder3</span><span class="sxs-lookup"><span data-stu-id="ed7f6-116">ISymUnmanagedBinder3 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder3-interface.md)
