---
title: Метод ISymUnmanagedVariable::GetAddressKind
ms.date: 03/30/2017
api_name:
- ISymUnmanagedVariable.GetAddressKind
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedVariable::GetAddressKind
helpviewer_keywords:
- GetAddressKind method [.NET Framework debugging]
- ISymUnmanagedVariable::GetAddressKind method [.NET Framework debugging]
ms.assetid: a71563c0-62f2-4eb4-970c-825d61827613
topic_type:
- apiref
ms.openlocfilehash: 4d2de38e5e506873a6db262dcec19c7af9d8a0d0
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74446095"
---
# <a name="isymunmanagedvariablegetaddresskind-method"></a><span data-ttu-id="a44d7-102">Метод ISymUnmanagedVariable::GetAddressKind</span><span class="sxs-lookup"><span data-stu-id="a44d7-102">ISymUnmanagedVariable::GetAddressKind Method</span></span>
<span data-ttu-id="a44d7-103">Возвращает тип адреса этой переменной.</span><span class="sxs-lookup"><span data-stu-id="a44d7-103">Gets the kind of address of this variable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a44d7-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a44d7-104">Syntax</span></span>  
  
```cpp  
HRESULT GetAddressKind(  
    [out, retval] ULONG32* pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a44d7-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="a44d7-105">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="a44d7-106">заполняет Указатель на `ULONG32`, который получает значение.</span><span class="sxs-lookup"><span data-stu-id="a44d7-106">[out] A pointer to a `ULONG32` that receives the value.</span></span> <span data-ttu-id="a44d7-107">Возможные значения определяются в перечислении [корсимаддркинд](../../../../docs/framework/unmanaged-api/diagnostics/corsymaddrkind-enumeration.md) .</span><span class="sxs-lookup"><span data-stu-id="a44d7-107">The possible values are defined in the [CorSymAddrKind](../../../../docs/framework/unmanaged-api/diagnostics/corsymaddrkind-enumeration.md) enumeration.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a44d7-108">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="a44d7-108">Return Value</span></span>  
 <span data-ttu-id="a44d7-109">S_OK, если метод выполнен. в противном случае E_FAIL или другой код ошибки.</span><span class="sxs-lookup"><span data-stu-id="a44d7-109">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a44d7-110">Требования</span><span class="sxs-lookup"><span data-stu-id="a44d7-110">Requirements</span></span>  
 <span data-ttu-id="a44d7-111">**Заголовок:** Корсим. idl, Корсим. h</span><span class="sxs-lookup"><span data-stu-id="a44d7-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a44d7-112">См. также:</span><span class="sxs-lookup"><span data-stu-id="a44d7-112">See also</span></span>

- [<span data-ttu-id="a44d7-113">Интерфейс ISymUnmanagedVariable</span><span class="sxs-lookup"><span data-stu-id="a44d7-113">ISymUnmanagedVariable Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-interface.md)
