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
ms.openlocfilehash: 77dec4332aa65f6125685db607169b3398bcab98
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74446053"
---
# <a name="isymunmanagedvariablegetname-method"></a><span data-ttu-id="462c5-102">Метод ISymUnmanagedVariable::GetName</span><span class="sxs-lookup"><span data-stu-id="462c5-102">ISymUnmanagedVariable::GetName Method</span></span>
<span data-ttu-id="462c5-103">Возвращает имя этой переменной.</span><span class="sxs-lookup"><span data-stu-id="462c5-103">Gets the name of this variable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="462c5-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="462c5-104">Syntax</span></span>  
  
```cpp  
HRESULT GetName(  
    [in]  ULONG32  cchName,  
    [out] ULONG32  *pcchName,  
    [out, size_is(cchName),  
        length_is(*pcchName)] WCHAR szName[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="462c5-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="462c5-105">Parameters</span></span>  
 `cchName`  
 <span data-ttu-id="462c5-106">окне Длина буфера, на который указывает параметр `pcchName`.</span><span class="sxs-lookup"><span data-stu-id="462c5-106">[in] The length of the buffer that the `pcchName` parameter points to.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="462c5-107">заполняет Указатель на `ULONG32`, который получает размер (в символах) буфера, необходимого для хранения имени, включая завершающее пустое значение.</span><span class="sxs-lookup"><span data-stu-id="462c5-107">[out] A pointer to a `ULONG32` that receives the size, in characters, of the buffer required to contain the name, including the null termination.</span></span>  
  
 `szName`  
 <span data-ttu-id="462c5-108">заполняет Буфер, в котором хранится имя.</span><span class="sxs-lookup"><span data-stu-id="462c5-108">[out] The buffer that stores the name.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="462c5-109">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="462c5-109">Return Value</span></span>  
 <span data-ttu-id="462c5-110">S_OK, если метод выполнен. в противном случае E_FAIL или другой код ошибки.</span><span class="sxs-lookup"><span data-stu-id="462c5-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="462c5-111">Требования</span><span class="sxs-lookup"><span data-stu-id="462c5-111">Requirements</span></span>  
 <span data-ttu-id="462c5-112">**Заголовок:** Корсим. idl, Корсим. h</span><span class="sxs-lookup"><span data-stu-id="462c5-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="462c5-113">См. также:</span><span class="sxs-lookup"><span data-stu-id="462c5-113">See also</span></span>

- [<span data-ttu-id="462c5-114">Интерфейс ISymUnmanagedVariable</span><span class="sxs-lookup"><span data-stu-id="462c5-114">ISymUnmanagedVariable Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-interface.md)
