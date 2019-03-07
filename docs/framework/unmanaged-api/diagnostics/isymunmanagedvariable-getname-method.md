---
title: Метод ISymUnmanagedVariable::GetName
ms.date: 03/30/2017
api_name:
- ISymUnmanagedVariable.GetName
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedVariable::GetName
helpviewer_keywords:
- GetName method, ISymUnmanagedVariable interface [.NET Framework debugging]
- ISymUnmanagedVariable::GetName method [.NET Framework debugging]
ms.assetid: eedf1ef0-9d4a-4847-a201-4e99572dfe5e
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 5aa6f01f161ce7c497cc103493e3bf4506fa3394
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2019
ms.locfileid: "57475025"
---
# <a name="isymunmanagedvariablegetname-method"></a><span data-ttu-id="885c2-102">Метод ISymUnmanagedVariable::GetName</span><span class="sxs-lookup"><span data-stu-id="885c2-102">ISymUnmanagedVariable::GetName Method</span></span>
<span data-ttu-id="885c2-103">Возвращает имя этой переменной.</span><span class="sxs-lookup"><span data-stu-id="885c2-103">Gets the name of this variable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="885c2-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="885c2-104">Syntax</span></span>  
  
```  
HRESULT GetName(  
    [in]  ULONG32  cchName,  
    [out] ULONG32  *pcchName,  
    [out, size_is(cchName),  
        length_is(*pcchName)] WCHAR szName[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="885c2-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="885c2-105">Parameters</span></span>  
 `cchName`  
 <span data-ttu-id="885c2-106">[in] Длина буфера, `pcchName` указывает параметр.</span><span class="sxs-lookup"><span data-stu-id="885c2-106">[in] The length of the buffer that the `pcchName` parameter points to.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="885c2-107">[out] Указатель на `ULONG32` размер, который получает в символах, буфера, требуемого для хранения имени, включая завершающимся нулевым значением.</span><span class="sxs-lookup"><span data-stu-id="885c2-107">[out] A pointer to a `ULONG32` that receives the size, in characters, of the buffer required to contain the name, including the null termination.</span></span>  
  
 `szName`  
 <span data-ttu-id="885c2-108">[out] Буфер, в котором хранится имя.</span><span class="sxs-lookup"><span data-stu-id="885c2-108">[out] The buffer that stores the name.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="885c2-109">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="885c2-109">Return Value</span></span>  
 <span data-ttu-id="885c2-110">Значение S_OK, если метод выполнен успешно; в противном случае — значение E_FAIL или другим кодом ошибки.</span><span class="sxs-lookup"><span data-stu-id="885c2-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="885c2-111">Требования</span><span class="sxs-lookup"><span data-stu-id="885c2-111">Requirements</span></span>  
 <span data-ttu-id="885c2-112">**Заголовок.** CorSym.idl CorSym.h</span><span class="sxs-lookup"><span data-stu-id="885c2-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="885c2-113">См. также</span><span class="sxs-lookup"><span data-stu-id="885c2-113">See also</span></span>
- [<span data-ttu-id="885c2-114">Интерфейс ISymUnmanagedVariable</span><span class="sxs-lookup"><span data-stu-id="885c2-114">ISymUnmanagedVariable Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-interface.md)
