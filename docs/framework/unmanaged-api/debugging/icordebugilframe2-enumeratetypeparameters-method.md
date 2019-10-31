---
title: Метод ICorDebugILFrame2::EnumerateTypeParameters
ms.date: 03/30/2017
api_name:
- ICorDebugILFrame2.EnumerateTypeParameters
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugILFrame2::EnumerateTypeParameters
helpviewer_keywords:
- EnumerateTypeParameters method, ICorDebugILFrame2 interface [.NET Framework debugging]
- ICorDebugILFrame2::EnumerateTypeParameters method [.NET Framework debugging]
ms.assetid: 722d0d74-e0df-491f-98c4-62d501dfaf6f
topic_type:
- apiref
ms.openlocfilehash: 715ff5d4a06b53361d550f04e5154023d0b641bb
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73095113"
---
# <a name="icordebugilframe2enumeratetypeparameters-method"></a><span data-ttu-id="27854-102">Метод ICorDebugILFrame2::EnumerateTypeParameters</span><span class="sxs-lookup"><span data-stu-id="27854-102">ICorDebugILFrame2::EnumerateTypeParameters Method</span></span>
<span data-ttu-id="27854-103">Возвращает объект ICorDebugTypeEnum, содержащий параметры <xref:System.Type> в этом кадре.</span><span class="sxs-lookup"><span data-stu-id="27854-103">Gets an ICorDebugTypeEnum object that contains the <xref:System.Type> parameters in this frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="27854-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="27854-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumerateTypeParameters (  
    [out] ICorDebugTypeEnum    **ppTyParEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="27854-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="27854-105">Parameters</span></span>  
 `ppTyParEnum`  
 <span data-ttu-id="27854-106">Указатель на адрес объекта интерфейса ICorDebugTypeEnum, который допускает перечисление параметров типа.</span><span class="sxs-lookup"><span data-stu-id="27854-106">A pointer to the address of a ICorDebugTypeEnum interface object that allows enumeration of type parameters.</span></span>  
  
 <span data-ttu-id="27854-107">Список параметров типа включает параметры типа класса (если они есть), за которыми следуют параметры типа метода (если они есть).</span><span class="sxs-lookup"><span data-stu-id="27854-107">The list of type parameters include the class type parameters (if any) followed by the method type parameters (if any).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="27854-108">Заметки</span><span class="sxs-lookup"><span data-stu-id="27854-108">Remarks</span></span>  
 <span data-ttu-id="27854-109">Используйте метод [IMetaDataImport2:: EnumGenericParams](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-enumgenericparams-method.md) , чтобы определить, сколько параметров типа класса и параметров типа метода содержит этот список.</span><span class="sxs-lookup"><span data-stu-id="27854-109">Use the [IMetaDataImport2::EnumGenericParams](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-enumgenericparams-method.md) method to determine how many class type parameters and method type parameters this list contains.</span></span>  
  
 <span data-ttu-id="27854-110">Параметры типа доступны не всегда.</span><span class="sxs-lookup"><span data-stu-id="27854-110">The type parameters are not always available.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="27854-111">Требования</span><span class="sxs-lookup"><span data-stu-id="27854-111">Requirements</span></span>  
 <span data-ttu-id="27854-112">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="27854-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="27854-113">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="27854-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="27854-114">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="27854-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="27854-115">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="27854-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
