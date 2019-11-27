---
title: Метод ISymUnmanagedWriter::OpenNamespace
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.OpenNamespace
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::OpenNamespace
helpviewer_keywords:
- ISymUnmanagedWriter::OpenNamespace method [.NET Framework debugging]
- OpenNamespace method [.NET Framework debugging]
ms.assetid: 426f4e4f-e60d-4ad1-b546-a10e3c55c283
topic_type:
- apiref
ms.openlocfilehash: acbd49de7362d9c05a609a2d870af100637e10ab
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74427908"
---
# <a name="isymunmanagedwriteropennamespace-method"></a><span data-ttu-id="fa34c-102">Метод ISymUnmanagedWriter::OpenNamespace</span><span class="sxs-lookup"><span data-stu-id="fa34c-102">ISymUnmanagedWriter::OpenNamespace Method</span></span>
<span data-ttu-id="fa34c-103">Открывает новое пространство имен.</span><span class="sxs-lookup"><span data-stu-id="fa34c-103">Opens a new namespace.</span></span> <span data-ttu-id="fa34c-104">Вызовите этот метод перед определением методов или переменных, которые занимают пространство имен.</span><span class="sxs-lookup"><span data-stu-id="fa34c-104">Call this method before defining methods or variables that occupy a namespace.</span></span> <span data-ttu-id="fa34c-105">Пространства имен могут быть вложенными.</span><span class="sxs-lookup"><span data-stu-id="fa34c-105">Namespaces can be nested.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fa34c-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="fa34c-106">Syntax</span></span>  
  
```cpp  
HRESULT OpenNamespace(  
    [in] const WCHAR *name);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fa34c-107">Параметры</span><span class="sxs-lookup"><span data-stu-id="fa34c-107">Parameters</span></span>  
 `name`  
 <span data-ttu-id="fa34c-108">окне Указатель на имя нового пространства имен.</span><span class="sxs-lookup"><span data-stu-id="fa34c-108">[in] A pointer to the name of the new namespace.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="fa34c-109">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="fa34c-109">Return Value</span></span>  
 <span data-ttu-id="fa34c-110">S_OK, если метод выполнен. в противном случае E_FAIL или другой код ошибки.</span><span class="sxs-lookup"><span data-stu-id="fa34c-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fa34c-111">Требования</span><span class="sxs-lookup"><span data-stu-id="fa34c-111">Requirements</span></span>  
 <span data-ttu-id="fa34c-112">**Заголовок:** Корсим. idl, Корсим. h</span><span class="sxs-lookup"><span data-stu-id="fa34c-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fa34c-113">См. также</span><span class="sxs-lookup"><span data-stu-id="fa34c-113">See also</span></span>

- [<span data-ttu-id="fa34c-114">Интерфейс ISymUnmanagedWriter</span><span class="sxs-lookup"><span data-stu-id="fa34c-114">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
- [<span data-ttu-id="fa34c-115">Метод CloseNamespace</span><span class="sxs-lookup"><span data-stu-id="fa34c-115">CloseNamespace Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-closenamespace-method.md)
