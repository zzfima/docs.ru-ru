---
title: Интерфейс ISymUnmanagedBinder3
ms.date: 03/30/2017
api_name:
- ISymUnmanagedBinder3
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedBinder3 Interface
helpviewer_keywords:
- ISymUnmanagedBinder3 interface [.NET Framework debugging]
ms.assetid: 37527a84-4b03-4f08-8135-94d898599089
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: be91591bfbbe4531c5518b90e560bc05457c92da
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54730169"
---
# <a name="isymunmanagedbinder3-interface"></a><span data-ttu-id="e94ae-102">Интерфейс ISymUnmanagedBinder3</span><span class="sxs-lookup"><span data-stu-id="e94ae-102">ISymUnmanagedBinder3 Interface</span></span>
<span data-ttu-id="e94ae-103">Расширяет интерфейс средства привязки символов.</span><span class="sxs-lookup"><span data-stu-id="e94ae-103">Extends the symbol binder interface.</span></span> <span data-ttu-id="e94ae-104">Получить этот интерфейс, вызвав `QueryInterface` на объект, реализующий `ISymUnmanagedBinder` интерфейс.</span><span class="sxs-lookup"><span data-stu-id="e94ae-104">Obtain this interface by calling `QueryInterface` on an object that implements the `ISymUnmanagedBinder` interface.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="e94ae-105">Он представляет угрозу безопасности, чтобы открыть файл базы данных (PDB) программы из ненадежного источника.</span><span class="sxs-lookup"><span data-stu-id="e94ae-105">It is a security risk to open a program database (PDB) file from an untrusted source.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="e94ae-106">Методы</span><span class="sxs-lookup"><span data-stu-id="e94ae-106">Methods</span></span>  
  
|<span data-ttu-id="e94ae-107">Метод</span><span class="sxs-lookup"><span data-stu-id="e94ae-107">Method</span></span>|<span data-ttu-id="e94ae-108">Описание</span><span class="sxs-lookup"><span data-stu-id="e94ae-108">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="e94ae-109">Метод GetReaderFromCallback</span><span class="sxs-lookup"><span data-stu-id="e94ae-109">GetReaderFromCallback Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder3-getreaderfromcallback-method.md)|<span data-ttu-id="e94ae-110">Пользователь может реализовывать или предоставить с помощью обратного вызова, либо `IID_IDiaReadExeAtRVACallback` или `IID_IDiaReadExeAtOffsetCallback` для получения сведения о каталоге отладки из памяти</span><span class="sxs-lookup"><span data-stu-id="e94ae-110">Allows the user to implement or supply via callback either an `IID_IDiaReadExeAtRVACallback` or `IID_IDiaReadExeAtOffsetCallback` to obtain the Debug directory information from memory</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="e94ae-111">Требования</span><span class="sxs-lookup"><span data-stu-id="e94ae-111">Requirements</span></span>  
 <span data-ttu-id="e94ae-112">**Заголовок.** CorSym.idl CorSym.h</span><span class="sxs-lookup"><span data-stu-id="e94ae-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e94ae-113">См. также</span><span class="sxs-lookup"><span data-stu-id="e94ae-113">See also</span></span>
- [<span data-ttu-id="e94ae-114">Интерфейсы хранилища символов диагностики</span><span class="sxs-lookup"><span data-stu-id="e94ae-114">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
- [<span data-ttu-id="e94ae-115">Интерфейс ISymUnmanagedBinder</span><span class="sxs-lookup"><span data-stu-id="e94ae-115">ISymUnmanagedBinder Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder-interface.md)
- [<span data-ttu-id="e94ae-116">Интерфейс ISymUnmanagedBinder2</span><span class="sxs-lookup"><span data-stu-id="e94ae-116">ISymUnmanagedBinder2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder2-interface.md)
