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
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59157512"
---
# <a name="isymunmanagedbinder3-interface"></a><span data-ttu-id="51522-102">Интерфейс ISymUnmanagedBinder3</span><span class="sxs-lookup"><span data-stu-id="51522-102">ISymUnmanagedBinder3 Interface</span></span>
<span data-ttu-id="51522-103">Расширяет интерфейс средства привязки символов.</span><span class="sxs-lookup"><span data-stu-id="51522-103">Extends the symbol binder interface.</span></span> <span data-ttu-id="51522-104">Получить этот интерфейс, вызвав `QueryInterface` на объект, реализующий `ISymUnmanagedBinder` интерфейс.</span><span class="sxs-lookup"><span data-stu-id="51522-104">Obtain this interface by calling `QueryInterface` on an object that implements the `ISymUnmanagedBinder` interface.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="51522-105">Он представляет угрозу безопасности, чтобы открыть файл базы данных (PDB) программы из ненадежного источника.</span><span class="sxs-lookup"><span data-stu-id="51522-105">It is a security risk to open a program database (PDB) file from an untrusted source.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="51522-106">Методы</span><span class="sxs-lookup"><span data-stu-id="51522-106">Methods</span></span>  
  
|<span data-ttu-id="51522-107">Метод</span><span class="sxs-lookup"><span data-stu-id="51522-107">Method</span></span>|<span data-ttu-id="51522-108">Описание</span><span class="sxs-lookup"><span data-stu-id="51522-108">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="51522-109">Метод GetReaderFromCallback</span><span class="sxs-lookup"><span data-stu-id="51522-109">GetReaderFromCallback Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder3-getreaderfromcallback-method.md)|<span data-ttu-id="51522-110">Пользователь может реализовывать или предоставить с помощью обратного вызова, либо `IID_IDiaReadExeAtRVACallback` или `IID_IDiaReadExeAtOffsetCallback` для получения сведения о каталоге отладки из памяти</span><span class="sxs-lookup"><span data-stu-id="51522-110">Allows the user to implement or supply via callback either an `IID_IDiaReadExeAtRVACallback` or `IID_IDiaReadExeAtOffsetCallback` to obtain the Debug directory information from memory</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="51522-111">Требования</span><span class="sxs-lookup"><span data-stu-id="51522-111">Requirements</span></span>  
 <span data-ttu-id="51522-112">**Заголовок.** CorSym.idl CorSym.h</span><span class="sxs-lookup"><span data-stu-id="51522-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="51522-113">См. также</span><span class="sxs-lookup"><span data-stu-id="51522-113">See also</span></span>

- [<span data-ttu-id="51522-114">Интерфейсы хранилища символов диагностики</span><span class="sxs-lookup"><span data-stu-id="51522-114">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
- [<span data-ttu-id="51522-115">Интерфейс ISymUnmanagedBinder</span><span class="sxs-lookup"><span data-stu-id="51522-115">ISymUnmanagedBinder Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder-interface.md)
- [<span data-ttu-id="51522-116">Интерфейс ISymUnmanagedBinder2</span><span class="sxs-lookup"><span data-stu-id="51522-116">ISymUnmanagedBinder2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder2-interface.md)
