---
title: Метод ISymUnmanagedScope::GetChildren
ms.date: 03/30/2017
api_name:
- ISymUnmanagedScope.GetChildren
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedScope::GetChildren
helpviewer_keywords:
- ISymUnmanagedScope::GetChildren method [.NET Framework debugging]
- GetChildren method [.NET Framework debugging]
ms.assetid: 0bed524e-cc48-4bf0-b9fa-25d665e63ddb
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 3ce2372be02bc0bae7097389d4933f1f28a4ed79
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33427054"
---
# <a name="isymunmanagedscopegetchildren-method"></a><span data-ttu-id="495f1-102">Метод ISymUnmanagedScope::GetChildren</span><span class="sxs-lookup"><span data-stu-id="495f1-102">ISymUnmanagedScope::GetChildren Method</span></span>
<span data-ttu-id="495f1-103">Получает дочерний объект этой области.</span><span class="sxs-lookup"><span data-stu-id="495f1-103">Gets the children of this scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="495f1-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="495f1-104">Syntax</span></span>  
  
```  
HRESULT GetChildren(  
    [in]  ULONG32  cChildren,  
    [out] ULONG32  *pcChildren,  
    [out, size_is(cChildren),  
        length_is(*pcChildren)] ISymUnmanagedScope* children[]);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="495f1-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="495f1-105">Parameters</span></span>  
 `cChildren`  
 <span data-ttu-id="495f1-106">[in] Объект `ULONG32` указывает размер `children` массива.</span><span class="sxs-lookup"><span data-stu-id="495f1-106">[in] A `ULONG32` that indicates the size of the `children` array.</span></span>  
  
 `pcChildren`  
 <span data-ttu-id="495f1-107">[out] Указатель на `ULONG32` , получающий размер буфера, необходимый для хранения дочерних элементов.</span><span class="sxs-lookup"><span data-stu-id="495f1-107">[out] A pointer to a `ULONG32` that receives the size of the buffer required to contain the children.</span></span>  
  
 `children`  
 <span data-ttu-id="495f1-108">[out] Возвращаемый массив дочерних элементов.</span><span class="sxs-lookup"><span data-stu-id="495f1-108">[out] The returned array of children.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="495f1-109">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="495f1-109">Return Value</span></span>  
 <span data-ttu-id="495f1-110">Значение S_OK, если метод выполнен успешно; в противном случае — значение E_FAIL или другим кодом ошибки.</span><span class="sxs-lookup"><span data-stu-id="495f1-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="495f1-111">Требования</span><span class="sxs-lookup"><span data-stu-id="495f1-111">Requirements</span></span>  
 <span data-ttu-id="495f1-112">**Заголовок:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="495f1-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="495f1-113">См. также</span><span class="sxs-lookup"><span data-stu-id="495f1-113">See Also</span></span>  
 [<span data-ttu-id="495f1-114">Интерфейс ISymUnmanagedScope</span><span class="sxs-lookup"><span data-stu-id="495f1-114">ISymUnmanagedScope Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-interface.md)  
 [<span data-ttu-id="495f1-115">Метод GetParent</span><span class="sxs-lookup"><span data-stu-id="495f1-115">GetParent Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-getparent-method.md)
