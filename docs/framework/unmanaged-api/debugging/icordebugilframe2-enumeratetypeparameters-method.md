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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f2e53bfb46579cc51b7ad88ef7de2b9f8d2f9390
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67758770"
---
# <a name="icordebugilframe2enumeratetypeparameters-method"></a><span data-ttu-id="95fe2-102">Метод ICorDebugILFrame2::EnumerateTypeParameters</span><span class="sxs-lookup"><span data-stu-id="95fe2-102">ICorDebugILFrame2::EnumerateTypeParameters Method</span></span>
<span data-ttu-id="95fe2-103">Возвращает объект, содержащий ICorDebugTypeEnum <xref:System.Type> параметры в этом кадре.</span><span class="sxs-lookup"><span data-stu-id="95fe2-103">Gets an ICorDebugTypeEnum object that contains the <xref:System.Type> parameters in this frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="95fe2-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="95fe2-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumerateTypeParameters (  
    [out] ICorDebugTypeEnum    **ppTyParEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="95fe2-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="95fe2-105">Parameters</span></span>  
 `ppTyParEnum`  
 <span data-ttu-id="95fe2-106">Указатель на адрес объекта интерфейса ICorDebugTypeEnum, позволяющий перечисления параметров типа.</span><span class="sxs-lookup"><span data-stu-id="95fe2-106">A pointer to the address of a ICorDebugTypeEnum interface object that allows enumeration of type parameters.</span></span>  
  
 <span data-ttu-id="95fe2-107">Список параметров типа включает параметры типа класса (если таковые имеются) следуют параметры типа метода (если таковые имеются).</span><span class="sxs-lookup"><span data-stu-id="95fe2-107">The list of type parameters include the class type parameters (if any) followed by the method type parameters (if any).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="95fe2-108">Примечания</span><span class="sxs-lookup"><span data-stu-id="95fe2-108">Remarks</span></span>  
 <span data-ttu-id="95fe2-109">Используйте [IMetaDataImport2::EnumGenericParams](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-enumgenericparams-method.md) метод, чтобы определить, сколько параметров типа класса и метода параметры, этот список содержит типа.</span><span class="sxs-lookup"><span data-stu-id="95fe2-109">Use the [IMetaDataImport2::EnumGenericParams](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-enumgenericparams-method.md) method to determine how many class type parameters and method type parameters this list contains.</span></span>  
  
 <span data-ttu-id="95fe2-110">Параметры типа не всегда доступны.</span><span class="sxs-lookup"><span data-stu-id="95fe2-110">The type parameters are not always available.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="95fe2-111">Требования</span><span class="sxs-lookup"><span data-stu-id="95fe2-111">Requirements</span></span>  
 <span data-ttu-id="95fe2-112">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="95fe2-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="95fe2-113">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="95fe2-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="95fe2-114">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="95fe2-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="95fe2-115">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="95fe2-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
