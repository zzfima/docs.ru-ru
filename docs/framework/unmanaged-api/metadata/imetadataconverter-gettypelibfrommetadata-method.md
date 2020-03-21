---
title: Метод IMetaDataConverter::GetTypeLibFromMetaData
ms.date: 03/30/2017
api_name:
- IMetaDataConverter.GetTypeLibFromMetaData
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataConverter::GetTypeLibFromMetaData
helpviewer_keywords:
- GetTypeLibFromMetaData method [.NET Framework metadata]
- IMetaDataConverter::GetTypeLibFromMetaData method [.NET Framework metadata]
ms.assetid: 90eab7b3-1fae-4af4-8bce-f7bc0e188a99
topic_type:
- apiref
ms.openlocfilehash: ef573eb9a572c27e685289b2740a55e898be2093
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177630"
---
# <a name="imetadataconvertergettypelibfrommetadata-method"></a><span data-ttu-id="3d6de-102">Метод IMetaDataConverter::GetTypeLibFromMetaData</span><span class="sxs-lookup"><span data-stu-id="3d6de-102">IMetaDataConverter::GetTypeLibFromMetaData Method</span></span>
<span data-ttu-id="3d6de-103">Получает указатель на `ITypeLib` экземпляр, представляющий библиотеку типов с указанными именами библиотеки и модуля.</span><span class="sxs-lookup"><span data-stu-id="3d6de-103">Gets a pointer to an `ITypeLib` instance that represents the type library that has the specified library and module names.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3d6de-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="3d6de-104">Syntax</span></span>  
  
```cpp  
HRESULT GetTypeLibFromMetaData (  
    [in]  BSTR     strModule,
    [in]  BSTR     strTlbName,
    [out] ITypeLib **ppITL  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3d6de-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="3d6de-105">Parameters</span></span>  
 `strModule`  
 <span data-ttu-id="3d6de-106">(в) Название модуля библиотеки типов.</span><span class="sxs-lookup"><span data-stu-id="3d6de-106">[in] The name of the type library's module.</span></span>  
  
 `strTlbName`  
 <span data-ttu-id="3d6de-107">(в) Название библиотеки типов.</span><span class="sxs-lookup"><span data-stu-id="3d6de-107">[in] The name of the type library.</span></span>  
  
 `ppITL`  
 <span data-ttu-id="3d6de-108">(ваут) Указатель на место, которое получает `ITypeLib` адрес экземпляра, представляющий библиотеку типов.</span><span class="sxs-lookup"><span data-stu-id="3d6de-108">[out] A pointer to a location that receives the address of the `ITypeLib` instance that represents the type library.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3d6de-109">Требования</span><span class="sxs-lookup"><span data-stu-id="3d6de-109">Requirements</span></span>  
 <span data-ttu-id="3d6de-110">**Платформа:** Смотрите [системные требования](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3d6de-110">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3d6de-111">**Заголовок:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="3d6de-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="3d6de-112">**Библиотека:** Используется в качестве ресурса в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="3d6de-112">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="3d6de-113">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3d6de-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3d6de-114">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="3d6de-114">See also</span></span>

- [<span data-ttu-id="3d6de-115">Интерфейс IMetaDataConverter</span><span class="sxs-lookup"><span data-stu-id="3d6de-115">IMetaDataConverter Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataconverter-interface.md)
