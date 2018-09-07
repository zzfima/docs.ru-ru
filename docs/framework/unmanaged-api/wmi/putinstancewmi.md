---
title: Функция PutInstanceWmi (Справочник по неуправляемым API)
description: Функция PutInstanceWmi создает или обновляет экземпляр существующего класса.
ms.date: 11/06/2017
api_name:
- PutInstanceWmi
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- PutInstanceWmi
helpviewer_keywords:
- PutInstanceWmi function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 67abf017040b9e6bbe9b10e560c8d57c124ae84e
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/06/2018
ms.locfileid: "43876220"
---
# <a name="putinstancewmi-function"></a>Функция PutInstanceWmi
Создает или обновляет экземпляр существующего класса. Экземпляр записывается в репозиторий WMI. 

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT PutInstanceWmi (
   [in] IWbemClassObject*    pInst,
   [in] long                 lFlags,
   [in] IWbemContext*        pCtx,
   [out] IWbemCallResult**   ppCallResult
); 
```  

## <a name="parameters"></a>Параметры

`pInst`    
[in] Указатель на экземпляр, чтобы быть записанный.

`lFlags`   
[in] Сочетание флагов, влияющих на поведение этой функции. Следующие значения определяются в *WbemCli.h* файл заголовка, или их можно определить как константы в коде: 

|Константа  |Значение  |Описание  |
|---------|---------|---------|
| `WBEM_FLAG_USE_AMENDED_QUALIFIERS` | 0x20000 | Если задано, WMI не хранит все квалификаторы с **Amended** flavor. </br> В противном случае набор, предполагается, что этот объект не локализовано, а все квалификаторы — storedwith данного экземпляра. |
| `WBEM_FLAG_CREATE_OR_UPDATE` | 0 | Создайте экземпляр, если он не существует, или заменяет его, если он уже существует. |
| `WBEM_FLAG_UPDATE_ONLY` | 1 | Обновите экземпляр. Экземпляр должен существовать для успешного вызова. |
| `WBEM_FLAG_CREATE_ONLY` | 2 | Создайте экземпляр. Вызов завершается неудачей, если экземпляр уже существует. |
| `WBEM_FLAG_RETURN_IMMEDIATELY` | 0x10 | Этот флаг приводит к Полусинхронный вызов. |

`pCtx`  
[in] Как правило, это значение равно `null`. В противном случае он является указателем на [IWbemContext](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemcontext) экземпляр, который может использоваться поставщиком, предоставляющего запрошенного классы. 

`ppCallResult`  
[out] Если `null`, этот параметр не используется. Если `lFlags` содержит `WBEM_FLAG_RETURN_IMMEDIATELY`, функция немедленно возвращает `WBEM_S_NO_ERROR`. `ppCallResult` Параметр получает указатель на новый [IWbemCallResult](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemcallresult) объекта.

## <a name="return-value"></a>Возвращаемое значение

Следующие значения, возвращаемые этой функцией, определяются в *WbemCli.h* файл заголовка, или их можно определить как константы в коде:

|Константа  |Значение  |Описание  |
|---------|---------|---------|
| `WBEM_E_ACCESS_DENIED` | 0x80041003 | Пользователь не имеет разрешения на обновление экземпляра указанного класса. |
| `WBEM_E_FAILED` | 0x80041001 | Произошла неизвестная ошибка. |
| `WBEM_E_INVALID_CLASS` | 0x80041010 | Класс, поддерживающий этот экземпляр не является допустимым. |
| `WBEM_E_ILLEGAL_NULL` | 0x80041028 | `null` был указан для свойства, которое не может быть `null`, например, помеченный атрибутом **индексированное** или **Not_Null** квалификатор. |
| `WBEM_E_INVALID_OBJECT` | 0x8004100f | Указанный экземпляр не является допустимым. (Например, вызов `PutInstanceWmi` с классом возвращает это значение.) |
| `WBEM_E_INVALID_PARAMETER` | 0x80041008 | Параметр не является допустимым. |
| `WBEM_E_ALREADY_EXISTS` | 0x80041019 | `WBEM_FLAG_CREATE_ONLY` Указан флаг, но экземпляр уже существует. |
| `WBEM_E_NOT_FOUND` | 0x80041002 | `WBEM_FLAG_UPDATE_ONLY` был указан в `lFlags`, но экземпляр не существует. |
| `WBEM_E_OUT_OF_MEMORY` | 0x80041006 | Недостаточно памяти для завершения операции. |
| `WBEM_E_SHUTTING_DOWN` | 0x80041033 | WMI был, вероятно, остановлена или перезапустить. Вызовите [ConnectServerWmi](connectserverwmi.md) еще раз. |
| `WBEM_E_TRANSPORT_FAILURE` | 0x80041015 | Сбой удаленной процедуры вызова (RPC) связь между текущим процессом и WMI. |
| `WBEM_S_NO_ERROR` | 0 | Вызов функции был успешным. |
  
## <a name="remarks"></a>Примечания

Эта функция создает оболочку для вызова [IWbemServices::PutInstance](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemservices-putinstance) метод.

`PutInstanceWmi` Функции поддерживается создание экземпляров и обновление экземпляров только существующих классов.  В зависимости от `pCtx` имеет параметр, будут обновлены некоторые или все свойства экземпляра. 

Когда экземпляр, на которые указывают `pInst` принадлежит вызовы всех поставщиков, ответственность за классы, от которых наследует подкласса подкласс управления Windows. Все эти поставщики должны успешно завершиться для первоначального `PutInstanceWmi` для успешного выполнения запроса. Сначала вызывается поставщик, поддерживающий класс верхним в иерархии. Порядок вызова продолжается с подклассом класса верхний и выполняется сверху вниз, пока не достигнет Windows управления поставщика для класса, владельца экземпляра, на которые указывают `pInst`.
Управление Windows не вызывает поставщики для любого дочернего класса экземпляра. 

Если приложение необходимо обновить экземпляр, который принадлежит к иерархии классов, `pInst` параметр должен указывать на экземпляр, содержащий свойства, которые можно изменить. То есть, рассмотрите возможность целевого экземпляра, которому принадлежит **ClassB**. **ClassB** экземпляра является производным от **ClassA**, и **ClassA** определяет свойство **PropA**. Если приложению требуется внести изменение значение **PropA** в **ClassB** экземпляр, он должен задать `pInst` этого экземпляра, а не экземпляр **ClassA** .

Вызов `PutInstanceWmi` на экземпляр абстрактного класса не допускается.

Если происходит сбой вызова функции, можно получить дополнительные сведения об ошибке, вызвав [GetErrorInfo](geterrorinfo.md) функции.

## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** WMINet_Utils.idl  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>См. также  
[WMI и счетчики производительности (Справочник по неуправляемым API)](index.md)
