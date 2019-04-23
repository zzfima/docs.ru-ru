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
ms.openlocfilehash: fdfd8e8fc419809a3a490639ada1c533f286fe8b
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59157512"
---
# <a name="isymunmanagedbinder3-interface"></a><span data-ttu-id="f2e16-102">Интерфейс ISymUnmanagedBinder3</span><span class="sxs-lookup"><span data-stu-id="f2e16-102">ISymUnmanagedBinder3 Interface</span></span>
<span data-ttu-id="f2e16-103">Расширяет интерфейс средства привязки символов.</span><span class="sxs-lookup"><span data-stu-id="f2e16-103">Extends the symbol binder interface.</span></span> <span data-ttu-id="f2e16-104">Получить этот интерфейс, вызвав `QueryInterface` на объект, реализующий `ISymUnmanagedBinder` интерфейс.</span><span class="sxs-lookup"><span data-stu-id="f2e16-104">Obtain this interface by calling `QueryInterface` on an object that implements the `ISymUnmanagedBinder` interface.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="f2e16-105">Он представляет угрозу безопасности, чтобы открыть файл базы данных (PDB) программы из ненадежного источника.</span><span class="sxs-lookup"><span data-stu-id="f2e16-105">It is a security risk to open a program database (PDB) file from an untrusted source.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="f2e16-106">Методы</span><span class="sxs-lookup"><span data-stu-id="f2e16-106">Methods</span></span>  
  
|<span data-ttu-id="f2e16-107">Метод</span><span class="sxs-lookup"><span data-stu-id="f2e16-107">Method</span></span>|<span data-ttu-id="f2e16-108">Описание</span><span class="sxs-lookup"><span data-stu-id="f2e16-108">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="f2e16-109">Метод GetReaderFromCallback</span><span class="sxs-lookup"><span data-stu-id="f2e16-109">GetReaderFromCallback Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder3-getreaderfromcallback-method.md)|<span data-ttu-id="f2e16-110">Пользователь может реализовывать или предоставить с помощью обратного вызова, либо `IID_IDiaReadExeAtRVACallback` или `IID_IDiaReadExeAtOffsetCallback` для получения сведения о каталоге отладки из памяти</span><span class="sxs-lookup"><span data-stu-id="f2e16-110">Allows the user to implement or supply via callback either an `IID_IDiaReadExeAtRVACallback` or `IID_IDiaReadExeAtOffsetCallback` to obtain the Debug directory information from memory</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="f2e16-111">Требования</span><span class="sxs-lookup"><span data-stu-id="f2e16-111">Requirements</span></span>  
 <span data-ttu-id="f2e16-112">**Заголовок.** CorSym.idl CorSym.h</span><span class="sxs-lookup"><span data-stu-id="f2e16-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f2e16-113">См. также</span><span class="sxs-lookup"><span data-stu-id="f2e16-113">See also</span></span>

- [<span data-ttu-id="f2e16-114">Интерфейсы хранилища символов диагностики</span><span class="sxs-lookup"><span data-stu-id="f2e16-114">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
- [<span data-ttu-id="f2e16-115">Интерфейс ISymUnmanagedBinder</span><span class="sxs-lookup"><span data-stu-id="f2e16-115">ISymUnmanagedBinder Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder-interface.md)
- [<span data-ttu-id="f2e16-116">Интерфейс ISymUnmanagedBinder2</span><span class="sxs-lookup"><span data-stu-id="f2e16-116">ISymUnmanagedBinder2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder2-interface.md)
