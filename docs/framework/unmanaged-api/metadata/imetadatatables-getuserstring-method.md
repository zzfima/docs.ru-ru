---
title: Метод IMetaDataTables::GetUserString
ms.date: 03/30/2017
api_name:
- IMetaDataTables.GetUserString
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataTables::GetUserString
helpviewer_keywords:
- IMetaDataTables::GetUserString method [.NET Framework metadata]
- GetUserString method, IMetaDataTables interface [.NET Framework metadata]
ms.assetid: 35b8f0d6-9aba-4714-adb2-62020a38fb7e
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 0d7dee3da1967f8a958ea95ab4555f279c962f51
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33451799"
---
# <a name="imetadatatablesgetuserstring-method"></a><span data-ttu-id="99628-102">Метод IMetaDataTables::GetUserString</span><span class="sxs-lookup"><span data-stu-id="99628-102">IMetaDataTables::GetUserString Method</span></span>
<span data-ttu-id="99628-103">Получает жестко заданная строка в столбце строки в текущей области по указанному индексу.</span><span class="sxs-lookup"><span data-stu-id="99628-103">Gets the hard-coded string at the specified index in the string column in the current scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="99628-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="99628-104">Syntax</span></span>  
  
```  
HRESULT GetUserString (  
    [in]  ULONG       ixUserString,  
    [out] ULONG       *pcbData,  
    [out] const void  **ppData  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="99628-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="99628-105">Parameters</span></span>  
 `ixUserString`  
 <span data-ttu-id="99628-106">[in] Значение индекса, из которого требуется извлечь жестко заданная строка.</span><span class="sxs-lookup"><span data-stu-id="99628-106">[in] The index value from which the hard-coded string will be retrieved.</span></span>  
  
 `pcbData`  
 <span data-ttu-id="99628-107">[out] P; ointer размер `ppData`.</span><span class="sxs-lookup"><span data-stu-id="99628-107">[out] A p;ointer to the size of `ppData`.</span></span>  
  
 `ppData`  
 <span data-ttu-id="99628-108">[out] Указатель на указатель возвращаемой строки.</span><span class="sxs-lookup"><span data-stu-id="99628-108">[out] A pointer to a pointer to the returned string.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="99628-109">Требования</span><span class="sxs-lookup"><span data-stu-id="99628-109">Requirements</span></span>  
 <span data-ttu-id="99628-110">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="99628-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="99628-111">**Заголовок:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="99628-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="99628-112">**Библиотека:** используется как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="99628-112">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="99628-113">**Версии платформы .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="99628-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="99628-114">См. также</span><span class="sxs-lookup"><span data-stu-id="99628-114">See Also</span></span>  
 [<span data-ttu-id="99628-115">Интерфейс IMetaDataTables</span><span class="sxs-lookup"><span data-stu-id="99628-115">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)  
 [<span data-ttu-id="99628-116">Интерфейс IMetaDataTables2</span><span class="sxs-lookup"><span data-stu-id="99628-116">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
