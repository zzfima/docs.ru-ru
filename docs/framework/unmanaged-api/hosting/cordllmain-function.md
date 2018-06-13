---
title: Функция _CorDllMain
ms.date: 03/30/2017
api_name:
- _CorDllMain
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- _CorDllMain
helpviewer_keywords:
- _CorDllMain function [.NET Framework hosting]
ms.assetid: bc7b51cf-39d3-48ec-a5cb-2f179fbefff8
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a5d541f834e829305fa2b091c45d0dc8f387bb55
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33431674"
---
# <a name="cordllmain-function"></a><span data-ttu-id="30674-102">Функция _CorDllMain</span><span class="sxs-lookup"><span data-stu-id="30674-102">_CorDllMain Function</span></span>
<span data-ttu-id="30674-103">Инициализирует общеязыковой среды выполнения (CLR), находит управляемую точку входа в заголовке CLR сборки DLL и начинает выполнение.</span><span class="sxs-lookup"><span data-stu-id="30674-103">Initializes the common language runtime (CLR), locates the managed entry point in the DLL assembly's CLR header, and begins execution.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="30674-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="30674-104">Syntax</span></span>  
  
```  
BOOL STDMETHODCALLTYPE _CorDllMain (  
   [in] HINSTANCE hInst,  
   [in] DWORD     dwReason,  
   [in] LPVOID    lpReserved  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="30674-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="30674-105">Parameters</span></span>  
 `hInst`  
 <span data-ttu-id="30674-106">[in] Дескриптор экземпляра загруженного модуля.</span><span class="sxs-lookup"><span data-stu-id="30674-106">[in] The instance handle of the loaded module.</span></span>  
  
 `dwReason`  
 <span data-ttu-id="30674-107">[in] Указывает, почему вызывается функция точки входа DLL.</span><span class="sxs-lookup"><span data-stu-id="30674-107">[in]Indicates why the DLL entry-point function is being called.</span></span> <span data-ttu-id="30674-108">Этот параметр может принимать одно из следующих значений: DLL_PROCESS_ATTACH, DLL_THREAD_ATTACH, DLL_THREAD_ATTACH или DLL_PROCESS_DETACH.</span><span class="sxs-lookup"><span data-stu-id="30674-108">This parameter can be one of the following values: DLL_PROCESS_ATTACH, DLL_THREAD_ATTACH, DLL_THREAD_ATTACH, or DLL_PROCESS_DETACH.</span></span> <span data-ttu-id="30674-109">Описание этих значений см. в разделе `DllMain` документации пакета Platform SDK.</span><span class="sxs-lookup"><span data-stu-id="30674-109">For descriptions of these values, see the `DllMain` documentation in the Platform SDK.</span></span>  
  
 `lpReserved`  
 <span data-ttu-id="30674-110">[in] Не используется.</span><span class="sxs-lookup"><span data-stu-id="30674-110">[in] Unused.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="30674-111">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="30674-111">Return Value</span></span>  
 <span data-ttu-id="30674-112">Этот метод возвращает `true` успеха и `false` при возникновении ошибки.</span><span class="sxs-lookup"><span data-stu-id="30674-112">This method returns `true` for success and `false` if an error occurs.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="30674-113">Примечания</span><span class="sxs-lookup"><span data-stu-id="30674-113">Remarks</span></span>  
 <span data-ttu-id="30674-114">Эта функция вызывается загрузчиком операционной системы для DLL-сборки.</span><span class="sxs-lookup"><span data-stu-id="30674-114">This function is called by the operating system loader for DLL assemblies.</span></span> <span data-ttu-id="30674-115">Для исполняемых сборок загрузчик вызывает [_CorExeMain](../../../../docs/framework/unmanaged-api/hosting/corexemain-function.md) вместо этого функцию.</span><span class="sxs-lookup"><span data-stu-id="30674-115">For executable assemblies, the loader calls the [_CorExeMain](../../../../docs/framework/unmanaged-api/hosting/corexemain-function.md) function instead.</span></span>  
  
 <span data-ttu-id="30674-116">Загрузчик операционной системы вызывает этот метод независимо от точки входа, указанной в DLL-файле.</span><span class="sxs-lookup"><span data-stu-id="30674-116">The operating system loader calls this method regardless of the entry point specified in the DLL file.</span></span>  
  
 <span data-ttu-id="30674-117">В Windows 98, Windows ME, Windows NT и Windows 2000 `_CorDllMain` функция косвенно через fixupin загрузчик операционной системы.</span><span class="sxs-lookup"><span data-stu-id="30674-117">In Windows 98, Windows ME, Windows NT, and Windows 2000, the `_CorDllMain` function is called indirectly through a fixupin the operating system loader.</span></span> <span data-ttu-id="30674-118">Во всех других версиях Windows он вызывается загрузчиком операционной системы.</span><span class="sxs-lookup"><span data-stu-id="30674-118">In all other versions of Windows, it is called directly by the operating system loader.</span></span>  
  
 <span data-ttu-id="30674-119">Дополнительные сведения см. в разделе «Примечания» в [_CorValidateImage](../../../../docs/framework/unmanaged-api/hosting/corvalidateimage-function.md) раздела.</span><span class="sxs-lookup"><span data-stu-id="30674-119">For additional information, see the Remarks section in the [_CorValidateImage](../../../../docs/framework/unmanaged-api/hosting/corvalidateimage-function.md) topic.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="30674-120">Требования</span><span class="sxs-lookup"><span data-stu-id="30674-120">Requirements</span></span>  
 <span data-ttu-id="30674-121">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="30674-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="30674-122">**Заголовок:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="30674-122">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="30674-123">**Библиотека:** включена как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="30674-123">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="30674-124">**Версии платформы .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="30674-124">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="30674-125">См. также</span><span class="sxs-lookup"><span data-stu-id="30674-125">See Also</span></span>  
 [<span data-ttu-id="30674-126">Глобальные статические функции метаданных</span><span class="sxs-lookup"><span data-stu-id="30674-126">Metadata Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-global-static-functions.md)
