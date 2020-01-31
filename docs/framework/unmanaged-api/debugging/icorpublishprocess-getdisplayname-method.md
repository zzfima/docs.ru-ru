---
title: Метод ICorPublishProcess::GetDisplayName
ms.date: 03/30/2017
api_name:
- ICorPublishProcess.GetDisplayName
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorPublishProcess::GetDisplayName
helpviewer_keywords:
- ICorPublishProcess::GetDisplayName method [.NET Framework debugging]
- GetDisplayName method, ICorPublishProcess interface [.NET Framework debugging]
ms.assetid: 7c0af9e9-a73f-41aa-a685-b21c439e059d
topic_type:
- apiref
ms.openlocfilehash: 7f2e644340a2ec7fe807830422b927ce811ddcf9
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76790562"
---
# <a name="icorpublishprocessgetdisplayname-method"></a><span data-ttu-id="3f251-102">Метод ICorPublishProcess::GetDisplayName</span><span class="sxs-lookup"><span data-stu-id="3f251-102">ICorPublishProcess::GetDisplayName Method</span></span>
<span data-ttu-id="3f251-103">Возвращает полный путь к исполняемому файлу для процесса, на который ссылается этот [ICorPublishProcess](icorpublishprocess-interface.md).</span><span class="sxs-lookup"><span data-stu-id="3f251-103">Gets the full path of the executable for the process referenced by this [ICorPublishProcess](icorpublishprocess-interface.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3f251-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="3f251-104">Syntax</span></span>  
  
```cpp  
HRESULT GetDisplayName (  
    [in]  ULONG32                    cchName,   
    [out] ULONG32                    *pcchName,  
    [out, size_is(cchName), length_is(*pcchName)]   
        WCHAR                        *szName  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3f251-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="3f251-105">Parameters</span></span>  
 `cchName`  
 <span data-ttu-id="3f251-106">[in] Размер массива `szName`.</span><span class="sxs-lookup"><span data-stu-id="3f251-106">[in] The size of the `szName` array.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="3f251-107">заполняет Число расширенных символов, возвращаемых в массиве `szName`.</span><span class="sxs-lookup"><span data-stu-id="3f251-107">[out] The number of wide characters returned in the `szName` array.</span></span>  
  
 `szName`  
 <span data-ttu-id="3f251-108">заполняет Массив для хранения имени исполняемого файла, включая полный путь к нему.</span><span class="sxs-lookup"><span data-stu-id="3f251-108">[out] An array to store the name, including the full path, of the executable.</span></span> <span data-ttu-id="3f251-109">Имя заканчивается нулем.</span><span class="sxs-lookup"><span data-stu-id="3f251-109">The name is null-terminated.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3f251-110">Требования</span><span class="sxs-lookup"><span data-stu-id="3f251-110">Requirements</span></span>  
 <span data-ttu-id="3f251-111">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3f251-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3f251-112">**Заголовок:** Корпуб. idl, Корпуб. h</span><span class="sxs-lookup"><span data-stu-id="3f251-112">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="3f251-113">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3f251-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3f251-114">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3f251-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3f251-115">См. также:</span><span class="sxs-lookup"><span data-stu-id="3f251-115">See also</span></span>

- [<span data-ttu-id="3f251-116">Интерфейс ICorPublishProcess</span><span class="sxs-lookup"><span data-stu-id="3f251-116">ICorPublishProcess Interface</span></span>](icorpublishprocess-interface.md)
