---
title: Метод IMetaDataImport::GetTypeSpecFromToken
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetTypeSpecFromToken
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetTypeSpecFromToken
helpviewer_keywords:
- GetTypeSpecFromToken method [.NET Framework metadata]
- IMetaDataImport::GetTypeSpecFromToken method [.NET Framework metadata]
ms.assetid: ee518bda-3296-482e-a7b7-e9d51dd1a181
topic_type:
- apiref
ms.openlocfilehash: 34b7cebfa063a3ad077b74a753fd37ba67ff53a5
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175321"
---
# <a name="imetadataimportgettypespecfromtoken-method"></a><span data-ttu-id="dec93-102">Метод IMetaDataImport::GetTypeSpecFromToken</span><span class="sxs-lookup"><span data-stu-id="dec93-102">IMetaDataImport::GetTypeSpecFromToken Method</span></span>
<span data-ttu-id="dec93-103">Возвращает двоичную подпись метаданных для спецификации типа, представленного указанным токеном.</span><span class="sxs-lookup"><span data-stu-id="dec93-103">Gets the binary metadata signature of the type specification represented by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dec93-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="dec93-104">Syntax</span></span>  
  
```cpp  
HRESULT GetTypeSpecFromToken (
   [in]  mdTypeSpec            typespec,
   [out] PCCOR_SIGNATURE       *ppvSig,
   [out] ULONG                 *pcbSig  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="dec93-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="dec93-105">Parameters</span></span>  
 `typespec`  
 <span data-ttu-id="dec93-106">(в) Токен TypeSpec, связанный с запрашиваемой подписью метаданных.</span><span class="sxs-lookup"><span data-stu-id="dec93-106">[in] The TypeSpec token associated with the requested metadata signature.</span></span>  
  
 `ppvSig`  
 <span data-ttu-id="dec93-107">(ваут) Указатель на двоичную подпись метаданных.</span><span class="sxs-lookup"><span data-stu-id="dec93-107">[out] A pointer to the binary metadata signature.</span></span>  
  
 `pcbSig`  
 <span data-ttu-id="dec93-108">(ваут) Размер, в байтах, подписи метаданных.</span><span class="sxs-lookup"><span data-stu-id="dec93-108">[out] The size, in bytes, of the metadata signature.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="dec93-109">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="dec93-109">Return Value</span></span>  
 <span data-ttu-id="dec93-110">HRESULT, указывающий на успех или неудачу.</span><span class="sxs-lookup"><span data-stu-id="dec93-110">An HRESULT that indicates success or failure.</span></span> <span data-ttu-id="dec93-111">Сбои могут быть протестированы с помощью макроса FAILED.</span><span class="sxs-lookup"><span data-stu-id="dec93-111">Failures can be tested with the FAILED macro.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dec93-112">Требования</span><span class="sxs-lookup"><span data-stu-id="dec93-112">Requirements</span></span>  
 <span data-ttu-id="dec93-113">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="dec93-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dec93-114">**Заголовок:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="dec93-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="dec93-115">**Библиотека:** Включено в качестве ресурса в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="dec93-115">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="dec93-116">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dec93-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dec93-117">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="dec93-117">See also</span></span>

- [<span data-ttu-id="dec93-118">Интерфейс IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="dec93-118">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="dec93-119">Интерфейс IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="dec93-119">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
