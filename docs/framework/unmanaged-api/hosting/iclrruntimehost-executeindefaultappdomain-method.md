---
title: Метод ICLRRuntimeHost::ExecuteInDefaultAppDomain
ms.date: 03/30/2017
api_name:
- ICLRRuntimeHost.ExecuteInDefaultAppDomain
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeHost::ExecuteInDefaultAppDomain
helpviewer_keywords:
- ICLRRuntimeHost::ExecuteInDefaultAppDomain method [.NET Framework hosting]
- ExecuteInDefaultAppDomain method [.NET Framework hosting]
ms.assetid: 30b5cf9a-a762-4bd4-be12-d6c1442b78b1
topic_type:
- apiref
ms.openlocfilehash: ed841d1b2ff346ebef668cbd96a58ddfe466b3b8
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73120438"
---
# <a name="iclrruntimehostexecuteindefaultappdomain-method"></a>Метод ICLRRuntimeHost::ExecuteInDefaultAppDomain
Вызывает указанный метод указанного типа в указанной управляемой сборке.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT ExecuteInDefaultAppDomain (  
    [in] LPCWSTR pwzAssemblyPath,  
    [in] LPCWSTR pwzTypeName,   
    [in] LPCWSTR pwzMethodName,  
    [in] LPCWSTR pwzArgument,  
    [out] DWORD *pReturnValue  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `pwzAssemblyPath`  
 окне Путь к <xref:System.Reflection.Assembly>, определяющий <xref:System.Type>, метод которого необходимо вызвать.  
  
 `pwzTypeName`  
 окне Имя <xref:System.Type>, определяющего вызываемый метод.  
  
 `pwzMethodName`  
 окне Имя вызываемого метода.  
  
 `pwzArgument`  
 окне Строковый параметр для передачи в метод.  
  
 `pReturnValue`  
 заполняет Целочисленное значение, возвращаемое вызванным методом.  
  
## <a name="return-value"></a>Возвращаемое значение  
  
|HRESULT|Описание|  
|-------------|-----------------|  
|S_OK|`ExecuteInDefaultAppDomain` успешно возвращено.|  
|HOST_E_CLRNOTAVAILABLE|Среда CLR не была загружена в процесс, или среда CLR находится в состоянии, в котором она не может выполнить управляемый код или успешно обработать вызов.|  
|HOST_E_TIMEOUT|Время ожидания вызова истекло.|  
|HOST_E_NOT_OWNER|Вызывающий объект не владеет блокировкой.|  
|HOST_E_ABANDONED|Событие было отменено, пока заблокированный поток или волокно ожидают его.|  
|E_FAIL|Произошла неизвестная фатальная ошибка. Если метод возвращает значение E_FAIL, список отзыва сертификатов больше не может использоваться в процессе. Последующие вызовы методов размещения возвращают HOST_E_CLRNOTAVAILABLE.|  
  
## <a name="remarks"></a>Заметки  
 Вызванный метод должен иметь следующую сигнатуру:  
  
```cpp  
static int pwzMethodName (String pwzArgument)  
```  
  
 где `pwzMethodName` представляет имя вызванного метода, а `pwzArgument` представляет строковое значение, передаваемое в качестве параметра этому методу. Если значение HRESULT равно S_OK, то `pReturnValue` устанавливается в целочисленное значение, возвращаемое вызванным методом. В противном случае `pReturnValue` не задано.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** MSCorEE. h  
  
 **Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICLRRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md)
