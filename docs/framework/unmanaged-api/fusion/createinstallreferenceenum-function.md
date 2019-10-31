---
title: Функция CreateInstallReferenceEnum
ms.date: 03/30/2017
api_name:
- CreateInstallReferenceEnum
api_location:
- fusion.dll
- clr.dll
- mscorwks.dll
api_type:
- DLLExport
f1_keywords:
- CreateInstallReference
helpviewer_keywords:
- CreateInstallReference function [.NET Framework fusion]
ms.assetid: 80dbbbf8-54fc-4894-b74a-0179d3201083
topic_type:
- apiref
ms.openlocfilehash: f089769f854bad5d3e572e0307734e06e72ca89c
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73108571"
---
# <a name="createinstallreferenceenum-function"></a><span data-ttu-id="88341-102">Функция CreateInstallReferenceEnum</span><span class="sxs-lookup"><span data-stu-id="88341-102">CreateInstallReferenceEnum Function</span></span>
<span data-ttu-id="88341-103">Возвращает указатель на экземпляр [IInstallReferenceEnum](iinstallreferenceenum-interface.md) , представляющий список ссылок приложения на указанную сборку.</span><span class="sxs-lookup"><span data-stu-id="88341-103">Gets a pointer to an [IInstallReferenceEnum](iinstallreferenceenum-interface.md) instance that represents a list of an application's references to the specified assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="88341-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="88341-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateInstallReferenceEnum (  
    [out] IInstallReferenceEnum **ppRefEnum,  
    [in]  IAssemblyName         *pName,  
    [in]  DWORD                 dwFlags,  
    [in]  LPVOID                pvReserved  
 );  
```  
  
## <a name="parameters"></a><span data-ttu-id="88341-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="88341-105">Parameters</span></span>  
 `ppRefEnum`  
 <span data-ttu-id="88341-106">заполняет Возвращаемый указатель `IInstallReferenceEnum`.</span><span class="sxs-lookup"><span data-stu-id="88341-106">[out] The returned `IInstallReferenceEnum` pointer.</span></span>  
  
 `pName`  
 <span data-ttu-id="88341-107">окне Объект [IAssemblyName](iassemblyname-interface.md) , определяющий сборку, для которой перечисляются ссылки.</span><span class="sxs-lookup"><span data-stu-id="88341-107">[in] The [IAssemblyName](iassemblyname-interface.md) that identifies the assembly for which to enumerate references.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="88341-108">окне Флаги, влияющие на поведение перечислителя.</span><span class="sxs-lookup"><span data-stu-id="88341-108">[in] Flags that influence the enumerator's behavior.</span></span>  
  
 `pvReserved`  
 <span data-ttu-id="88341-109">окне Зарезервировано для будущего расширения.</span><span class="sxs-lookup"><span data-stu-id="88341-109">[in] Reserved for future extensibility.</span></span> <span data-ttu-id="88341-110">`pvReserved` должен быть пустой ссылкой.</span><span class="sxs-lookup"><span data-stu-id="88341-110">`pvReserved` must be a null reference.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="88341-111">Требования</span><span class="sxs-lookup"><span data-stu-id="88341-111">Requirements</span></span>  
 <span data-ttu-id="88341-112">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="88341-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="88341-113">**Заголовок:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="88341-113">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="88341-114">**Библиотека:** Fusion. dll и mscorwks. dll.</span><span class="sxs-lookup"><span data-stu-id="88341-114">**Library:** Fusion.dll and Mscorwks.dll.</span></span> <span data-ttu-id="88341-115">Используйте Fusion. dll вместо Mscorwks. dll, чтобы обеспечить правильную версию .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="88341-115">Use Fusion.dll instead of Mscorwks.dll to ensure that you target the correct version of the .NET Framework.</span></span>  
  
 <span data-ttu-id="88341-116">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="88341-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="88341-117">См. также</span><span class="sxs-lookup"><span data-stu-id="88341-117">See also</span></span>

- [<span data-ttu-id="88341-118">Интерфейс IInstallReferenceEnum</span><span class="sxs-lookup"><span data-stu-id="88341-118">IInstallReferenceEnum Interface</span></span>](iinstallreferenceenum-interface.md)
- [<span data-ttu-id="88341-119">Интерфейс IAssemblyName</span><span class="sxs-lookup"><span data-stu-id="88341-119">IAssemblyName Interface</span></span>](iassemblyname-interface.md)
- [<span data-ttu-id="88341-120">Глобальные статические функции Fusion</span><span class="sxs-lookup"><span data-stu-id="88341-120">Fusion Global Static Functions</span></span>](fusion-global-static-functions.md)
