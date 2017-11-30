---
title: "Интерфейс ISymUnmanagedBinder3"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedBinder3
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedBinder3 Interface
helpviewer_keywords: ISymUnmanagedBinder3 interface [.NET Framework debugging]
ms.assetid: 37527a84-4b03-4f08-8135-94d898599089
topic_type: apiref
caps.latest.revision: "7"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: df5cd6d4015fad1baf98909ee9cc923cd9bce05e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="isymunmanagedbinder3-interface"></a><span data-ttu-id="53768-102">Интерфейс ISymUnmanagedBinder3</span><span class="sxs-lookup"><span data-stu-id="53768-102">ISymUnmanagedBinder3 Interface</span></span>
<span data-ttu-id="53768-103">Расширяет интерфейс средства привязки символов.</span><span class="sxs-lookup"><span data-stu-id="53768-103">Extends the symbol binder interface.</span></span> <span data-ttu-id="53768-104">Получить этот интерфейс, вызвав `QueryInterface` на объект, реализующий интерфейс `ISymUnmanagedBinder` интерфейс.</span><span class="sxs-lookup"><span data-stu-id="53768-104">Obtain this interface by calling `QueryInterface` on an object that implements the `ISymUnmanagedBinder` interface.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="53768-105">Он представляет угрозу безопасности, чтобы открыть файл программы (PDB) из ненадежного источника.</span><span class="sxs-lookup"><span data-stu-id="53768-105">It is a security risk to open a program database (PDB) file from an untrusted source.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="53768-106">Методы</span><span class="sxs-lookup"><span data-stu-id="53768-106">Methods</span></span>  
  
|<span data-ttu-id="53768-107">Метод</span><span class="sxs-lookup"><span data-stu-id="53768-107">Method</span></span>|<span data-ttu-id="53768-108">Описание</span><span class="sxs-lookup"><span data-stu-id="53768-108">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="53768-109">Метод GetReaderFromCallback</span><span class="sxs-lookup"><span data-stu-id="53768-109">GetReaderFromCallback Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder3-getreaderfromcallback-method.md)|<span data-ttu-id="53768-110">Пользователь может реализовать или указать через обратный вызов, либо `IID_IDiaReadExeAtRVACallback` или `IID_IDiaReadExeAtOffsetCallback` для получения отладочной информации каталога из памяти</span><span class="sxs-lookup"><span data-stu-id="53768-110">Allows the user to implement or supply via callback either an `IID_IDiaReadExeAtRVACallback` or `IID_IDiaReadExeAtOffsetCallback` to obtain the Debug directory information from memory</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="53768-111">Требования</span><span class="sxs-lookup"><span data-stu-id="53768-111">Requirements</span></span>  
 <span data-ttu-id="53768-112">**Заголовок:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="53768-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="53768-113">См. также</span><span class="sxs-lookup"><span data-stu-id="53768-113">See Also</span></span>  
 [<span data-ttu-id="53768-114">Интерфейсы хранилища символов диагностики</span><span class="sxs-lookup"><span data-stu-id="53768-114">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)  
 [<span data-ttu-id="53768-115">Интерфейс ISymUnmanagedBinder</span><span class="sxs-lookup"><span data-stu-id="53768-115">ISymUnmanagedBinder Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder-interface.md)  
 [<span data-ttu-id="53768-116">Интерфейс ISymUnmanagedBinder2</span><span class="sxs-lookup"><span data-stu-id="53768-116">ISymUnmanagedBinder2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder2-interface.md)
