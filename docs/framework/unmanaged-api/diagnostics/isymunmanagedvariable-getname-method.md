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
ms.openlocfilehash: 6323b7d94ca32646d3aa63af6d3efc4de95e67fb
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54534531"
---
# <a name="isymunmanagedvariablegetname-method"></a><span data-ttu-id="384be-102">Метод ISymUnmanagedVariable::GetName</span><span class="sxs-lookup"><span data-stu-id="384be-102">ISymUnmanagedVariable::GetName Method</span></span>
<span data-ttu-id="384be-103">Возвращает имя этой переменной.</span><span class="sxs-lookup"><span data-stu-id="384be-103">Gets the name of this variable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="384be-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="384be-104">Syntax</span></span>  
  
```  
HRESULT GetName(  
    [in]  ULONG32  cchName,  
    [out] ULONG32  *pcchName,  
    [out, size_is(cchName),  
        length_is(*pcchName)] WCHAR szName[]);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="384be-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="384be-105">Parameters</span></span>  
 `cchName`  
 <span data-ttu-id="384be-106">[in] Длина буфера, `pcchName` указывает параметр.</span><span class="sxs-lookup"><span data-stu-id="384be-106">[in] The length of the buffer that the `pcchName` parameter points to.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="384be-107">[out] Указатель на `ULONG32` размер, который получает в символах, буфера, требуемого для хранения имени, включая завершающимся нулевым значением.</span><span class="sxs-lookup"><span data-stu-id="384be-107">[out] A pointer to a `ULONG32` that receives the size, in characters, of the buffer required to contain the name, including the null termination.</span></span>  
  
 `szName`  
 <span data-ttu-id="384be-108">[out] Буфер, в котором хранится имя.</span><span class="sxs-lookup"><span data-stu-id="384be-108">[out] The buffer that stores the name.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="384be-109">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="384be-109">Return Value</span></span>  
 <span data-ttu-id="384be-110">Значение S_OK, если метод выполнен успешно; в противном случае — значение E_FAIL или другим кодом ошибки.</span><span class="sxs-lookup"><span data-stu-id="384be-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="384be-111">Требования</span><span class="sxs-lookup"><span data-stu-id="384be-111">Requirements</span></span>  
 <span data-ttu-id="384be-112">**Заголовок.** CorSym.idl CorSym.h</span><span class="sxs-lookup"><span data-stu-id="384be-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="384be-113">См. также</span><span class="sxs-lookup"><span data-stu-id="384be-113">See also</span></span>
- [<span data-ttu-id="384be-114">Интерфейс ISymUnmanagedVariable</span><span class="sxs-lookup"><span data-stu-id="384be-114">ISymUnmanagedVariable Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-interface.md)
