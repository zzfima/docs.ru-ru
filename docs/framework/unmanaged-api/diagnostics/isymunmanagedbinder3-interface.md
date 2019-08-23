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
ms.openlocfilehash: a6f514cc070a0a38eb09a5387efc8611100765b5
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69944094"
---
# <a name="isymunmanagedbinder3-interface"></a><span data-ttu-id="f4da4-102">Интерфейс ISymUnmanagedBinder3</span><span class="sxs-lookup"><span data-stu-id="f4da4-102">ISymUnmanagedBinder3 Interface</span></span>
<span data-ttu-id="f4da4-103">Расширяет интерфейс связывателя символов.</span><span class="sxs-lookup"><span data-stu-id="f4da4-103">Extends the symbol binder interface.</span></span> <span data-ttu-id="f4da4-104">Получите этот интерфейс, вызвав метод `QueryInterface` для объекта, который `ISymUnmanagedBinder` реализует интерфейс.</span><span class="sxs-lookup"><span data-stu-id="f4da4-104">Obtain this interface by calling `QueryInterface` on an object that implements the `ISymUnmanagedBinder` interface.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="f4da4-105">При открытии файла базы данных программы (PDB) из ненадежного источника возникает угроза безопасности.</span><span class="sxs-lookup"><span data-stu-id="f4da4-105">It is a security risk to open a program database (PDB) file from an untrusted source.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="f4da4-106">Методы</span><span class="sxs-lookup"><span data-stu-id="f4da4-106">Methods</span></span>  
  
|<span data-ttu-id="f4da4-107">Метод</span><span class="sxs-lookup"><span data-stu-id="f4da4-107">Method</span></span>|<span data-ttu-id="f4da4-108">Описание</span><span class="sxs-lookup"><span data-stu-id="f4da4-108">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="f4da4-109">Метод GetReaderFromCallback</span><span class="sxs-lookup"><span data-stu-id="f4da4-109">GetReaderFromCallback Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder3-getreaderfromcallback-method.md)|<span data-ttu-id="f4da4-110">Позволяет пользователю реализовать или предоставить через обратный вызов либо `IID_IDiaReadExeAtRVACallback` `IID_IDiaReadExeAtOffsetCallback` для получения сведений о каталоге отладки из памяти.</span><span class="sxs-lookup"><span data-stu-id="f4da4-110">Allows the user to implement or supply via callback either an `IID_IDiaReadExeAtRVACallback` or `IID_IDiaReadExeAtOffsetCallback` to obtain the Debug directory information from memory</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="f4da4-111">Требования</span><span class="sxs-lookup"><span data-stu-id="f4da4-111">Requirements</span></span>  
 <span data-ttu-id="f4da4-112">**Заголовок.** Корсим. idl, Корсим. h</span><span class="sxs-lookup"><span data-stu-id="f4da4-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f4da4-113">См. также</span><span class="sxs-lookup"><span data-stu-id="f4da4-113">See also</span></span>

- [<span data-ttu-id="f4da4-114">Интерфейсы хранилища символов диагностики</span><span class="sxs-lookup"><span data-stu-id="f4da4-114">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
- [<span data-ttu-id="f4da4-115">Интерфейс ISymUnmanagedBinder</span><span class="sxs-lookup"><span data-stu-id="f4da4-115">ISymUnmanagedBinder Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder-interface.md)
- [<span data-ttu-id="f4da4-116">Интерфейс ISymUnmanagedBinder2</span><span class="sxs-lookup"><span data-stu-id="f4da4-116">ISymUnmanagedBinder2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder2-interface.md)
