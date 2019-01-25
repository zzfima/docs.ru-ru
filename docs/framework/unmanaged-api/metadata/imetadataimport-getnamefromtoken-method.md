---
title: Метод IMetaDataImport::GetNameFromToken
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetNameFromToken
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetNameFromToken
helpviewer_keywords:
- GetNameFromToken method [.NET Framework metadata]
- IMetaDataImport::GetNameFromToken method [.NET Framework metadata]
ms.assetid: 32114ecf-8916-4ab2-a201-179c017344f1
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 36218fa44f1cb49d8d0193d7c72e6feb2d121050
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54718849"
---
# <a name="imetadataimportgetnamefromtoken-method"></a><span data-ttu-id="c6442-102">Метод IMetaDataImport::GetNameFromToken</span><span class="sxs-lookup"><span data-stu-id="c6442-102">IMetaDataImport::GetNameFromToken Method</span></span>
<span data-ttu-id="c6442-103">Возвращает имя объекта, на который ссылается указанный токен метаданных, в формате UTF-8.</span><span class="sxs-lookup"><span data-stu-id="c6442-103">Gets the UTF-8 name of the object referenced by the specified metadata token.</span></span> <span data-ttu-id="c6442-104">Этот метод устарел.</span><span class="sxs-lookup"><span data-stu-id="c6442-104">This method is obsolete.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c6442-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c6442-105">Syntax</span></span>  
  
```  
HRESULT GetNameFromToken (  
   [in] mdToken      tk,  
   [out] MDUTF8CSTR  *pszUtf8NamePtr  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c6442-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="c6442-106">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="c6442-107">[in] Токен, представляющий имя возвращаемого объекта.</span><span class="sxs-lookup"><span data-stu-id="c6442-107">[in] The token representing the object to return the name for.</span></span>  
  
 `pszUtf8NamePtr`  
 <span data-ttu-id="c6442-108">[out] Указатель на имя объекта UTF-8 в куче.</span><span class="sxs-lookup"><span data-stu-id="c6442-108">[out] A pointer to the UTF-8 object name in the heap.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c6442-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="c6442-109">Remarks</span></span>  
 <span data-ttu-id="c6442-110">`GetNameFromToken` устарел.</span><span class="sxs-lookup"><span data-stu-id="c6442-110">`GetNameFromToken` is obsolete.</span></span> <span data-ttu-id="c6442-111">Кроме того, вызовите метод, чтобы получить свойства конкретного типа необходим, такие как токен `GetFieldProps` для поля или `GetMethodProps` для метода.</span><span class="sxs-lookup"><span data-stu-id="c6442-111">As an alternative, call a method to get the properties of the particular type of token required, such as `GetFieldProps` for a field or `GetMethodProps` for a method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c6442-112">Требования</span><span class="sxs-lookup"><span data-stu-id="c6442-112">Requirements</span></span>  
 <span data-ttu-id="c6442-113">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c6442-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c6442-114">**Заголовок.** Cor.h</span><span class="sxs-lookup"><span data-stu-id="c6442-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="c6442-115">**Библиотека:** Включена как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="c6442-115">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="c6442-116">**Версии платформы .NET framework:** 1.0</span><span class="sxs-lookup"><span data-stu-id="c6442-116">**.NET Framework Versions:** 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c6442-117">См. также</span><span class="sxs-lookup"><span data-stu-id="c6442-117">See also</span></span>
- [<span data-ttu-id="c6442-118">Интерфейс IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="c6442-118">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="c6442-119">Интерфейс IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="c6442-119">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
