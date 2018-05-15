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
ms.openlocfilehash: 06a4d5b1b108c15fa7ee4a7f5270b73f7adc1e6f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="isymunmanagedbinder3-interface"></a><span data-ttu-id="43878-102">Интерфейс ISymUnmanagedBinder3</span><span class="sxs-lookup"><span data-stu-id="43878-102">ISymUnmanagedBinder3 Interface</span></span>
<span data-ttu-id="43878-103">Расширяет интерфейс средства привязки символов.</span><span class="sxs-lookup"><span data-stu-id="43878-103">Extends the symbol binder interface.</span></span> <span data-ttu-id="43878-104">Получить этот интерфейс, вызвав `QueryInterface` на объект, реализующий интерфейс `ISymUnmanagedBinder` интерфейс.</span><span class="sxs-lookup"><span data-stu-id="43878-104">Obtain this interface by calling `QueryInterface` on an object that implements the `ISymUnmanagedBinder` interface.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="43878-105">Он представляет угрозу безопасности, чтобы открыть файл программы (PDB) из ненадежного источника.</span><span class="sxs-lookup"><span data-stu-id="43878-105">It is a security risk to open a program database (PDB) file from an untrusted source.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="43878-106">Методы</span><span class="sxs-lookup"><span data-stu-id="43878-106">Methods</span></span>  
  
|<span data-ttu-id="43878-107">Метод</span><span class="sxs-lookup"><span data-stu-id="43878-107">Method</span></span>|<span data-ttu-id="43878-108">Описание</span><span class="sxs-lookup"><span data-stu-id="43878-108">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="43878-109">Метод GetReaderFromCallback</span><span class="sxs-lookup"><span data-stu-id="43878-109">GetReaderFromCallback Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder3-getreaderfromcallback-method.md)|<span data-ttu-id="43878-110">Пользователь может реализовать или указать через обратный вызов, либо `IID_IDiaReadExeAtRVACallback` или `IID_IDiaReadExeAtOffsetCallback` для получения отладочной информации каталога из памяти</span><span class="sxs-lookup"><span data-stu-id="43878-110">Allows the user to implement or supply via callback either an `IID_IDiaReadExeAtRVACallback` or `IID_IDiaReadExeAtOffsetCallback` to obtain the Debug directory information from memory</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="43878-111">Требования</span><span class="sxs-lookup"><span data-stu-id="43878-111">Requirements</span></span>  
 <span data-ttu-id="43878-112">**Заголовок:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="43878-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="43878-113">См. также</span><span class="sxs-lookup"><span data-stu-id="43878-113">See Also</span></span>  
 [<span data-ttu-id="43878-114">Интерфейсы хранилища символов диагностики</span><span class="sxs-lookup"><span data-stu-id="43878-114">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)  
 [<span data-ttu-id="43878-115">Интерфейс ISymUnmanagedBinder</span><span class="sxs-lookup"><span data-stu-id="43878-115">ISymUnmanagedBinder Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder-interface.md)  
 [<span data-ttu-id="43878-116">Интерфейс ISymUnmanagedBinder2</span><span class="sxs-lookup"><span data-stu-id="43878-116">ISymUnmanagedBinder2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder2-interface.md)
