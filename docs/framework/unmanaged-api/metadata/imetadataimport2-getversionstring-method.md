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
ms.openlocfilehash: 3b4c7ef2beca06713c04c7e0f8e30a47b884bf5c
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2019
ms.locfileid: "57486294"
---
# <a name="imetadataimport2getversionstring-method"></a><span data-ttu-id="2ebd0-102">Метод IMetaDataImport2::GetVersionString</span><span class="sxs-lookup"><span data-stu-id="2ebd0-102">IMetaDataImport2::GetVersionString Method</span></span>
<span data-ttu-id="2ebd0-103">Получает номер версии среды выполнения, которая использовалась для построения сборки.</span><span class="sxs-lookup"><span data-stu-id="2ebd0-103">Gets the version number of the runtime that was used to build the assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2ebd0-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="2ebd0-104">Syntax</span></span>  
  
```  
HRESULT GetVersionString (  
   [out] LPWSTR      pwzBuf,  
   [in]  DWORD       ccBufSize,  
   [out] DWORD       *pccBufSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2ebd0-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="2ebd0-105">Parameters</span></span>  
 `pwzBuf`  
 <span data-ttu-id="2ebd0-106">[out] Массив для хранения строки, в которой указывается версия.</span><span class="sxs-lookup"><span data-stu-id="2ebd0-106">[out] An array to store the string that specifies the version.</span></span>  
  
 `ccBufSize`  
 <span data-ttu-id="2ebd0-107">[in] Размер в расширенные символы из `pwzBuf` массива.</span><span class="sxs-lookup"><span data-stu-id="2ebd0-107">[in] The size, in wide characters, of the `pwzBuf` array.</span></span>  
  
 `pccBufSize`  
 <span data-ttu-id="2ebd0-108">[out] Число расширенных символов, включая завершающий нуль-символ, возвращенных в `pwzBuf` массива.</span><span class="sxs-lookup"><span data-stu-id="2ebd0-108">[out] The number of wide characters, including a null terminator, returned in the `pwzBuf` array.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2ebd0-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="2ebd0-109">Remarks</span></span>  
 <span data-ttu-id="2ebd0-110">`GetVersionString` Метод получает версию построения для текущей области метаданных.</span><span class="sxs-lookup"><span data-stu-id="2ebd0-110">The `GetVersionString` method gets the built-for version of the current metadata scope.</span></span> <span data-ttu-id="2ebd0-111">Если область никогда не был сохранен, он не будет иметь версию построения и возвращается пустая строка.</span><span class="sxs-lookup"><span data-stu-id="2ebd0-111">If the scope has never been saved, it will not have a built-for version, and an empty string will be returned.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2ebd0-112">Требования</span><span class="sxs-lookup"><span data-stu-id="2ebd0-112">Requirements</span></span>  
 <span data-ttu-id="2ebd0-113">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2ebd0-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2ebd0-114">**Заголовок.** Cor.h</span><span class="sxs-lookup"><span data-stu-id="2ebd0-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="2ebd0-115">**Библиотека:** Используется как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="2ebd0-115">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="2ebd0-116">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2ebd0-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2ebd0-117">См. также</span><span class="sxs-lookup"><span data-stu-id="2ebd0-117">See also</span></span>
- [<span data-ttu-id="2ebd0-118">Интерфейс IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="2ebd0-118">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
- [<span data-ttu-id="2ebd0-119">Интерфейс IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="2ebd0-119">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
