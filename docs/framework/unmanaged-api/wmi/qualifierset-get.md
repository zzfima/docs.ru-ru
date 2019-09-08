---
title: Функция QualifierSet_Get (Справочник по неуправляемым API)
description: Функция QualifierSet_Get Возвращает именованный квалификатор.
ms.date: 11/06/2017
api_name:
- QualifierSet_Get
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- QualifierSet_Get
helpviewer_keywords:
- QualifierSet_Get function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 751694985248346187eff016ef7a4a8054cb1212
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2019
ms.locfileid: "70798310"
---
# <a name="qualifierset_get-function"></a><span data-ttu-id="bfc72-103">Функция QualifierSet_Get</span><span class="sxs-lookup"><span data-stu-id="bfc72-103">QualifierSet_Get function</span></span>
<span data-ttu-id="bfc72-104">Получает указанный именованный квалификатор.</span><span class="sxs-lookup"><span data-stu-id="bfc72-104">Gets the specified named qualifier.</span></span>  

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="bfc72-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="bfc72-105">Syntax</span></span>  
  
```cpp  
HRESULT QualifierSet_Get (
   [in] int                  vFunc, 
   [in] IWbemQualifierSet*   ptr, 
   [in] LPCWSTR              wszName,
   [in] LONG                 lFlags,
   [out] VARIANT*            pVal,
   [out] LONG*               plFlavor                 
); 
```  

## <a name="parameters"></a><span data-ttu-id="bfc72-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="bfc72-106">Parameters</span></span>

`vFunc`   
<span data-ttu-id="bfc72-107">окне Этот параметр не используется.</span><span class="sxs-lookup"><span data-stu-id="bfc72-107">[in] This parameter is unused.</span></span>

`ptr`   
<span data-ttu-id="bfc72-108">окне Указатель на экземпляр [ивбемкуалифиерсет](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) .</span><span class="sxs-lookup"><span data-stu-id="bfc72-108">[in] A pointer to an [IWbemQualifierSet](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) instance.</span></span>

`wszName`   
<span data-ttu-id="bfc72-109">окне Имя квалификатора, значение которого запрашивается.</span><span class="sxs-lookup"><span data-stu-id="bfc72-109">[in] The name of the qualifier whose value is requested.</span></span>

`lFlags`   
<span data-ttu-id="bfc72-110">[in] Зарезервировано.</span><span class="sxs-lookup"><span data-stu-id="bfc72-110">[in] Reserved.</span></span> <span data-ttu-id="bfc72-111">Этот параметр должен иметь значение 0.</span><span class="sxs-lookup"><span data-stu-id="bfc72-111">This parameter must be 0.</span></span>

`pVal`   
<span data-ttu-id="bfc72-112">заполняет При успешном выполнении, правильный тип и значение для квалификатора.</span><span class="sxs-lookup"><span data-stu-id="bfc72-112">[out] When successful, the correct type and value for the qualifier.</span></span> <span data-ttu-id="bfc72-113">Если функция завершается ошибкой, `VARIANT` то, на `pVal` которую указывает, не изменяется.</span><span class="sxs-lookup"><span data-stu-id="bfc72-113">If the function fails, the `VARIANT` pointed to by `pVal` is not modified.</span></span> <span data-ttu-id="bfc72-114">Если этот параметр имеет `null`значение, параметр игнорируется.</span><span class="sxs-lookup"><span data-stu-id="bfc72-114">If this parameter is `null`, the parameter is ignored.</span></span>

`plFlavor`   
<span data-ttu-id="bfc72-115">заполняет Указатель на значение типа LONG, которое получает биты флагов для запрошенного описателя.</span><span class="sxs-lookup"><span data-stu-id="bfc72-115">[out] A pointer to a LONG that receives the qualifier flavor bits for the requested qualifier.</span></span> <span data-ttu-id="bfc72-116">Если сведения о разновидностях не нужны, этот параметр может `null`иметь значение.</span><span class="sxs-lookup"><span data-stu-id="bfc72-116">If flavor information is not desired, this parameter can be `null`.</span></span> 

## <a name="return-value"></a><span data-ttu-id="bfc72-117">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="bfc72-117">Return value</span></span>

<span data-ttu-id="bfc72-118">Следующие значения, возвращаемые этой функцией, определены в файле заголовка *вбемкли. h* , или их можно определить как константы в коде:</span><span class="sxs-lookup"><span data-stu-id="bfc72-118">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="bfc72-119">Константа</span><span class="sxs-lookup"><span data-stu-id="bfc72-119">Constant</span></span>  |<span data-ttu-id="bfc72-120">Значение</span><span class="sxs-lookup"><span data-stu-id="bfc72-120">Value</span></span>  |<span data-ttu-id="bfc72-121">Описание</span><span class="sxs-lookup"><span data-stu-id="bfc72-121">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="bfc72-122">0x80041008</span><span class="sxs-lookup"><span data-stu-id="bfc72-122">0x80041008</span></span> | <span data-ttu-id="bfc72-123">Недопустимый параметр.</span><span class="sxs-lookup"><span data-stu-id="bfc72-123">A parameter is not valid.</span></span> |
|`WBEM_E_NOT_FOUND` | <span data-ttu-id="bfc72-124">0x80041002</span><span class="sxs-lookup"><span data-stu-id="bfc72-124">0x80041002</span></span> | <span data-ttu-id="bfc72-125">Указанный квалификатор не существует.</span><span class="sxs-lookup"><span data-stu-id="bfc72-125">The specified qualifier does not exist.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="bfc72-126">0</span><span class="sxs-lookup"><span data-stu-id="bfc72-126">0</span></span> | <span data-ttu-id="bfc72-127">Вызов функции выполнен успешно.</span><span class="sxs-lookup"><span data-stu-id="bfc72-127">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="bfc72-128">Примечания</span><span class="sxs-lookup"><span data-stu-id="bfc72-128">Remarks</span></span>

<span data-ttu-id="bfc72-129">Эта функция заключает в оболочку вызов метода [ивбемкуалифиерсет:: Get](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemqualifierset-get) .</span><span class="sxs-lookup"><span data-stu-id="bfc72-129">This function wraps a call to the [IWbemQualifierSet::Get](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemqualifierset-get) method.</span></span>

## <a name="requirements"></a><span data-ttu-id="bfc72-130">Требования</span><span class="sxs-lookup"><span data-stu-id="bfc72-130">Requirements</span></span>  
 <span data-ttu-id="bfc72-131">**Платформ** См. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bfc72-131">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bfc72-132">**Заголовок.** WMINet_Utils. idl</span><span class="sxs-lookup"><span data-stu-id="bfc72-132">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="bfc72-133">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="bfc72-133">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bfc72-134">См. также</span><span class="sxs-lookup"><span data-stu-id="bfc72-134">See also</span></span>

- [<span data-ttu-id="bfc72-135">WMI и счетчики производительности (Справочник по неуправляемым интерфейсам API)</span><span class="sxs-lookup"><span data-stu-id="bfc72-135">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
