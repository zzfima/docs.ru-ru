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
ms.openlocfilehash: 8298e7240052bdd859dbe414281d8e78984342e8
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67778256"
---
# <a name="isymunmanagedvariablegetname-method"></a><span data-ttu-id="f064d-102">Метод ISymUnmanagedVariable::GetName</span><span class="sxs-lookup"><span data-stu-id="f064d-102">ISymUnmanagedVariable::GetName Method</span></span>
<span data-ttu-id="f064d-103">Возвращает имя этой переменной.</span><span class="sxs-lookup"><span data-stu-id="f064d-103">Gets the name of this variable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f064d-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f064d-104">Syntax</span></span>  
  
```cpp  
HRESULT GetName(  
    [in]  ULONG32  cchName,  
    [out] ULONG32  *pcchName,  
    [out, size_is(cchName),  
        length_is(*pcchName)] WCHAR szName[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f064d-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="f064d-105">Parameters</span></span>  
 `cchName`  
 <span data-ttu-id="f064d-106">[in] Длина буфера, `pcchName` указывает параметр.</span><span class="sxs-lookup"><span data-stu-id="f064d-106">[in] The length of the buffer that the `pcchName` parameter points to.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="f064d-107">[out] Указатель на `ULONG32` размер, который получает в символах, буфера, требуемого для хранения имени, включая завершающимся нулевым значением.</span><span class="sxs-lookup"><span data-stu-id="f064d-107">[out] A pointer to a `ULONG32` that receives the size, in characters, of the buffer required to contain the name, including the null termination.</span></span>  
  
 `szName`  
 <span data-ttu-id="f064d-108">[out] Буфер, в котором хранится имя.</span><span class="sxs-lookup"><span data-stu-id="f064d-108">[out] The buffer that stores the name.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f064d-109">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="f064d-109">Return Value</span></span>  
 <span data-ttu-id="f064d-110">Значение S_OK, если метод выполнен успешно; в противном случае — значение E_FAIL или другим кодом ошибки.</span><span class="sxs-lookup"><span data-stu-id="f064d-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f064d-111">Требования</span><span class="sxs-lookup"><span data-stu-id="f064d-111">Requirements</span></span>  
 <span data-ttu-id="f064d-112">**Заголовок.** CorSym.idl CorSym.h</span><span class="sxs-lookup"><span data-stu-id="f064d-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f064d-113">См. также</span><span class="sxs-lookup"><span data-stu-id="f064d-113">See also</span></span>

- [<span data-ttu-id="f064d-114">Интерфейс ISymUnmanagedVariable</span><span class="sxs-lookup"><span data-stu-id="f064d-114">ISymUnmanagedVariable Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-interface.md)
