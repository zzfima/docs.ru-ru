---
title: Метод IMetaDataImport::GetFieldMarshal
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetFieldMarshal
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetFieldMarshal
helpviewer_keywords:
- GetFieldMarshal method [.NET Framework metadata]
- IMetaDataImport::GetFieldMarshal method [.NET Framework metadata]
ms.assetid: 4e2d88c6-8a3a-4fbe-900b-b4f4c06bf6bf
topic_type:
- apiref
ms.openlocfilehash: 1a4f7703536bcfdae75b0bcffae8dca0734e9e0f
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74437564"
---
# <a name="imetadataimportgetfieldmarshal-method"></a><span data-ttu-id="06ea6-102">Метод IMetaDataImport::GetFieldMarshal</span><span class="sxs-lookup"><span data-stu-id="06ea6-102">IMetaDataImport::GetFieldMarshal Method</span></span>
<span data-ttu-id="06ea6-103">Возвращает указатель на собственный неуправляемый тип поля, представленного заданным токеном метаданных поля.</span><span class="sxs-lookup"><span data-stu-id="06ea6-103">Gets a pointer to the native, unmanaged type of the field represented by the specified field metadata token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="06ea6-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="06ea6-104">Syntax</span></span>  
  
```cpp  
HRESULT GetFieldMarshal (  
   [in]  mdToken             tk,   
   [out] PCCOR_SIGNATURE     *ppvNativeType,  
   [out] ULONG               *pcbNativeType   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="06ea6-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="06ea6-105">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="06ea6-106">окне Токен метаданных, представляющий поле, для которого необходимо получить сведения о маршалинге взаимодействия.</span><span class="sxs-lookup"><span data-stu-id="06ea6-106">[in] The metadata token that represents the field to get interop marshaling information for.</span></span>  
  
 `ppvNativeType`  
 <span data-ttu-id="06ea6-107">заполняет Указатель на сигнатуру метаданных собственного типа поля.</span><span class="sxs-lookup"><span data-stu-id="06ea6-107">[out] A pointer to the metadata signature of the field's native type.</span></span>  
  
 `pcbNativeType`  
 <span data-ttu-id="06ea6-108">заполняет Размер в байтах `ppvNativeType`.</span><span class="sxs-lookup"><span data-stu-id="06ea6-108">[out] The size in bytes of `ppvNativeType`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="06ea6-109">Требования</span><span class="sxs-lookup"><span data-stu-id="06ea6-109">Requirements</span></span>  
 <span data-ttu-id="06ea6-110">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="06ea6-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="06ea6-111">**Заголовок:** COR. h</span><span class="sxs-lookup"><span data-stu-id="06ea6-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="06ea6-112">**Библиотека:** Включается в качестве ресурса в библиотеку MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="06ea6-112">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="06ea6-113">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="06ea6-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="06ea6-114">См. также</span><span class="sxs-lookup"><span data-stu-id="06ea6-114">See also</span></span>

- [<span data-ttu-id="06ea6-115">Интерфейс IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="06ea6-115">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="06ea6-116">Интерфейс IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="06ea6-116">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
