---
title: Метод SetManifestFile
ms.date: 03/30/2017
api_name:
- IALink3.SetManifestFile
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- SetManifestFile
helpviewer_keywords:
- SetManifestFile method
ms.assetid: 1b33de4c-19cb-4a36-a93f-8675b2a36d58
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 8307960166cfc668a577431d688c439f0f794be2
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59072432"
---
# <a name="setmanifestfile-method"></a><span data-ttu-id="3d674-102">Метод SetManifestFile</span><span class="sxs-lookup"><span data-stu-id="3d674-102">SetManifestFile Method</span></span>
<span data-ttu-id="3d674-103">Позволяет задать или сбросить файл манифеста, компоновщик использует при создании сборки.</span><span class="sxs-lookup"><span data-stu-id="3d674-103">Enables you to specify or reset the manifest file that the linker uses when it creates the assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3d674-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="3d674-104">Syntax</span></span>  
  
```  
HRESULT SetManifestFile(  
    LPCWSTR pszFile  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="3d674-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="3d674-105">Parameters</span></span>  
 `pszFile`  
  
 <span data-ttu-id="3d674-106">Имя файла манифеста, содержимое которого помещаются в большой двоичный объект ресурсов Win32.</span><span class="sxs-lookup"><span data-stu-id="3d674-106">The name of the manifest file whose contents are put into the Win32 resources blob.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3d674-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="3d674-107">Return Value</span></span>  
 <span data-ttu-id="3d674-108">Возвращает S_OK, если метод выполнен успешно.</span><span class="sxs-lookup"><span data-stu-id="3d674-108">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3d674-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="3d674-109">Remarks</span></span>  
 <span data-ttu-id="3d674-110">Вызовите это перед запросом Win32ResBlob.</span><span class="sxs-lookup"><span data-stu-id="3d674-110">Call this before asking for the Win32ResBlob.</span></span> <span data-ttu-id="3d674-111">Значение `pszFile` параметр является имя файла манифеста, содержимое которого считывается и помещается в ресурсы Win32 с Идентификатором RT_MANIFEST.</span><span class="sxs-lookup"><span data-stu-id="3d674-111">The value of the `pszFile` parameter is the name of the manifest file whose contents are read and put in the Win32 resources with ID of RT_MANIFEST.</span></span> <span data-ttu-id="3d674-112">При вызове с помощью параметра значение NULL, все ранее считанного манифест очищается.</span><span class="sxs-lookup"><span data-stu-id="3d674-112">When called by using a parameter of NULL, any previously read manifest is cleared.</span></span> <span data-ttu-id="3d674-113">Это позволяет сбросить состояние компоновщика, чтобы во время инициализации.</span><span class="sxs-lookup"><span data-stu-id="3d674-113">This enables one to reset the state of the linker to that of initialization time.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3d674-114">Требования</span><span class="sxs-lookup"><span data-stu-id="3d674-114">Requirements</span></span>  
 <span data-ttu-id="3d674-115">Требуется aLink.h</span><span class="sxs-lookup"><span data-stu-id="3d674-115">Requires aLink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3d674-116">См. также</span><span class="sxs-lookup"><span data-stu-id="3d674-116">See also</span></span>

- [<span data-ttu-id="3d674-117">Интерфейс IALink3</span><span class="sxs-lookup"><span data-stu-id="3d674-117">IALink3 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink3-interface.md)
- [<span data-ttu-id="3d674-118">API ALink</span><span class="sxs-lookup"><span data-stu-id="3d674-118">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
- [<span data-ttu-id="3d674-119">Интерфейс IALink</span><span class="sxs-lookup"><span data-stu-id="3d674-119">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="3d674-120">Al.exe (компоновщик сборок)</span><span class="sxs-lookup"><span data-stu-id="3d674-120">Al.exe (Assembly Linker)</span></span>](../../../../docs/framework/tools/al-exe-assembly-linker.md)
