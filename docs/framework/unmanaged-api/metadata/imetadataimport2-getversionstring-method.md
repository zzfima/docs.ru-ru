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
ms.openlocfilehash: 0c9f667edf30feb23e1cdaa28950503283fce42e
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74445224"
---
# <a name="imetadataimport2getversionstring-method"></a><span data-ttu-id="9cc90-102">Метод IMetaDataImport2::GetVersionString</span><span class="sxs-lookup"><span data-stu-id="9cc90-102">IMetaDataImport2::GetVersionString Method</span></span>
<span data-ttu-id="9cc90-103">Возвращает номер версии среды выполнения, которая использовалась для построения сборки.</span><span class="sxs-lookup"><span data-stu-id="9cc90-103">Gets the version number of the runtime that was used to build the assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9cc90-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="9cc90-104">Syntax</span></span>  
  
```cpp  
HRESULT GetVersionString (  
   [out] LPWSTR      pwzBuf,  
   [in]  DWORD       ccBufSize,  
   [out] DWORD       *pccBufSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9cc90-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="9cc90-105">Parameters</span></span>  
 `pwzBuf`  
 <span data-ttu-id="9cc90-106">заполняет Массив для хранения строки, указывающей версию.</span><span class="sxs-lookup"><span data-stu-id="9cc90-106">[out] An array to store the string that specifies the version.</span></span>  
  
 `ccBufSize`  
 <span data-ttu-id="9cc90-107">окне Размер массива `pwzBuf` в расширенных символах.</span><span class="sxs-lookup"><span data-stu-id="9cc90-107">[in] The size, in wide characters, of the `pwzBuf` array.</span></span>  
  
 `pccBufSize`  
 <span data-ttu-id="9cc90-108">заполняет Число расширенных символов, включая знак завершения null, возвращенный в массиве `pwzBuf`.</span><span class="sxs-lookup"><span data-stu-id="9cc90-108">[out] The number of wide characters, including a null terminator, returned in the `pwzBuf` array.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9cc90-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="9cc90-109">Remarks</span></span>  
 <span data-ttu-id="9cc90-110">Метод `GetVersionString` получает встроенную версию текущей области метаданных.</span><span class="sxs-lookup"><span data-stu-id="9cc90-110">The `GetVersionString` method gets the built-for version of the current metadata scope.</span></span> <span data-ttu-id="9cc90-111">Если область не была сохранена, она не будет иметь встроенной версии и будет возвращена пустая строка.</span><span class="sxs-lookup"><span data-stu-id="9cc90-111">If the scope has never been saved, it will not have a built-for version, and an empty string will be returned.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9cc90-112">Требования</span><span class="sxs-lookup"><span data-stu-id="9cc90-112">Requirements</span></span>  
 <span data-ttu-id="9cc90-113">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9cc90-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9cc90-114">**Заголовок:** COR. h</span><span class="sxs-lookup"><span data-stu-id="9cc90-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="9cc90-115">**Библиотека:** Используется в качестве ресурса в MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="9cc90-115">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="9cc90-116">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9cc90-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9cc90-117">См. также:</span><span class="sxs-lookup"><span data-stu-id="9cc90-117">See also</span></span>

- [<span data-ttu-id="9cc90-118">Интерфейс IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="9cc90-118">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
- [<span data-ttu-id="9cc90-119">Интерфейс IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="9cc90-119">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
