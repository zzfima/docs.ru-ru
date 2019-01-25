---
title: Метод IMetaDataImport2::GetVersionString
ms.date: 03/30/2017
api_name:
- IMetaDataImport2.GetVersionString
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport2::GetVersionString
helpviewer_keywords:
- GetVersionString method, IMetaDataImport2 interface [.NET Framework metadata]
- IMetaDataImport2::GetVersionString method [.NET Framework metadata]
ms.assetid: 308183ee-fd44-4432-9d86-ef00d181b49b
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 5e041efed929255d4ce3af2d051a391bc4179cda
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54630922"
---
# <a name="imetadataimport2getversionstring-method"></a><span data-ttu-id="4e9cb-102">Метод IMetaDataImport2::GetVersionString</span><span class="sxs-lookup"><span data-stu-id="4e9cb-102">IMetaDataImport2::GetVersionString Method</span></span>
<span data-ttu-id="4e9cb-103">Получает номер версии среды выполнения, которая использовалась для построения сборки.</span><span class="sxs-lookup"><span data-stu-id="4e9cb-103">Gets the version number of the runtime that was used to build the assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4e9cb-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="4e9cb-104">Syntax</span></span>  
  
```  
HRESULT GetVersionString (  
   [out] LPWSTR      pwzBuf,  
   [in]  DWORD       ccBufSize,  
   [out] DWORD       *pccBufSize  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="4e9cb-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="4e9cb-105">Parameters</span></span>  
 `pwzBuf`  
 <span data-ttu-id="4e9cb-106">[out] Массив для хранения строки, в которой указывается версия.</span><span class="sxs-lookup"><span data-stu-id="4e9cb-106">[out] An array to store the string that specifies the version.</span></span>  
  
 `ccBufSize`  
 <span data-ttu-id="4e9cb-107">[in] Размер в расширенные символы из `pwzBuf` массива.</span><span class="sxs-lookup"><span data-stu-id="4e9cb-107">[in] The size, in wide characters, of the `pwzBuf` array.</span></span>  
  
 `pccBufSize`  
 <span data-ttu-id="4e9cb-108">[out] Число расширенных символов, включая завершающий нуль-символ, возвращенных в `pwzBuf` массива.</span><span class="sxs-lookup"><span data-stu-id="4e9cb-108">[out] The number of wide characters, including a null terminator, returned in the `pwzBuf` array.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4e9cb-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="4e9cb-109">Remarks</span></span>  
 <span data-ttu-id="4e9cb-110">`GetVersionString` Метод получает версию построения для текущей области метаданных.</span><span class="sxs-lookup"><span data-stu-id="4e9cb-110">The `GetVersionString` method gets the built-for version of the current metadata scope.</span></span> <span data-ttu-id="4e9cb-111">Если область никогда не был сохранен, он не будет иметь версию построения и возвращается пустая строка.</span><span class="sxs-lookup"><span data-stu-id="4e9cb-111">If the scope has never been saved, it will not have a built-for version, and an empty string will be returned.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4e9cb-112">Требования</span><span class="sxs-lookup"><span data-stu-id="4e9cb-112">Requirements</span></span>  
 <span data-ttu-id="4e9cb-113">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4e9cb-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4e9cb-114">**Заголовок.** Cor.h</span><span class="sxs-lookup"><span data-stu-id="4e9cb-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="4e9cb-115">**Библиотека:** Используется как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="4e9cb-115">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="4e9cb-116">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4e9cb-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4e9cb-117">См. также</span><span class="sxs-lookup"><span data-stu-id="4e9cb-117">See also</span></span>
- [<span data-ttu-id="4e9cb-118">Интерфейс IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="4e9cb-118">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
- [<span data-ttu-id="4e9cb-119">Интерфейс IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="4e9cb-119">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
