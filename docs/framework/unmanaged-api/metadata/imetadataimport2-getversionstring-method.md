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
ms.openlocfilehash: a01b4203145f6ffee4e3a11a3526f0b83e3dc741
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59154626"
---
# <a name="imetadataimport2getversionstring-method"></a><span data-ttu-id="08161-102">Метод IMetaDataImport2::GetVersionString</span><span class="sxs-lookup"><span data-stu-id="08161-102">IMetaDataImport2::GetVersionString Method</span></span>
<span data-ttu-id="08161-103">Получает номер версии среды выполнения, которая использовалась для построения сборки.</span><span class="sxs-lookup"><span data-stu-id="08161-103">Gets the version number of the runtime that was used to build the assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="08161-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="08161-104">Syntax</span></span>  
  
```  
HRESULT GetVersionString (  
   [out] LPWSTR      pwzBuf,  
   [in]  DWORD       ccBufSize,  
   [out] DWORD       *pccBufSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="08161-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="08161-105">Parameters</span></span>  
 `pwzBuf`  
 <span data-ttu-id="08161-106">[out] Массив для хранения строки, в которой указывается версия.</span><span class="sxs-lookup"><span data-stu-id="08161-106">[out] An array to store the string that specifies the version.</span></span>  
  
 `ccBufSize`  
 <span data-ttu-id="08161-107">[in] Размер в расширенные символы из `pwzBuf` массива.</span><span class="sxs-lookup"><span data-stu-id="08161-107">[in] The size, in wide characters, of the `pwzBuf` array.</span></span>  
  
 `pccBufSize`  
 <span data-ttu-id="08161-108">[out] Число расширенных символов, включая завершающий нуль-символ, возвращенных в `pwzBuf` массива.</span><span class="sxs-lookup"><span data-stu-id="08161-108">[out] The number of wide characters, including a null terminator, returned in the `pwzBuf` array.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="08161-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="08161-109">Remarks</span></span>  
 <span data-ttu-id="08161-110">`GetVersionString` Метод получает версию построения для текущей области метаданных.</span><span class="sxs-lookup"><span data-stu-id="08161-110">The `GetVersionString` method gets the built-for version of the current metadata scope.</span></span> <span data-ttu-id="08161-111">Если область никогда не был сохранен, он не будет иметь версию построения и возвращается пустая строка.</span><span class="sxs-lookup"><span data-stu-id="08161-111">If the scope has never been saved, it will not have a built-for version, and an empty string will be returned.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="08161-112">Требования</span><span class="sxs-lookup"><span data-stu-id="08161-112">Requirements</span></span>  
 <span data-ttu-id="08161-113">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="08161-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="08161-114">**Заголовок.** Cor.h</span><span class="sxs-lookup"><span data-stu-id="08161-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="08161-115">**Библиотека:** Используется как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="08161-115">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 **<span data-ttu-id="08161-116">Версии платформы .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="08161-116">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="08161-117">См. также</span><span class="sxs-lookup"><span data-stu-id="08161-117">See also</span></span>

- [<span data-ttu-id="08161-118">Интерфейс IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="08161-118">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
- [<span data-ttu-id="08161-119">Интерфейс IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="08161-119">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
