---
title: Метод IMetaDataEmit::DefineMethod
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DefineMethod
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DefineMethod
helpviewer_keywords:
- DefineMethod method [.NET Framework metadata]
- IMetaDataEmit::DefineMethod method [.NET Framework metadata]
ms.assetid: 3e2102c5-48b7-4c0e-b805-7e2b5e156e3d
topic_type:
- apiref
ms.openlocfilehash: d4f3c95428d6f0f8807e284c5b54582428176511
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177666"
---
# <a name="imetadataemitdefinemethod-method"></a>Метод IMetaDataEmit::DefineMethod
Создает определение для метода или глобальной функции с указанной подписью и возвращает маркер к определению этого метода.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT DefineMethod (
    [in]  mdTypeDef         td,
    [in]  LPCWSTR           szName,
    [in]  DWORD             dwMethodFlags,
    [in]  PCCOR_SIGNATURE   pvSigBlob,
    [in]  ULONG             cbSigBlob,
    [in]  ULONG             ulCodeRVA,
    [in]  DWORD             dwImplFlags,
    [out] mdMethodDef      *pmd  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `td`  
 (в) Токен `mdTypedef` родительского класса или интерфейс родительского интерфейса метода. Установите, `td` `mdTokenNil`если вы определяете глобальную функцию.  
  
 `szName`  
 (в) Имя участника в Unicode.  
  
 `dwMethodFlags`  
 (в) Значение перечисления [CorMethodAttr,](../../../../docs/framework/unmanaged-api/metadata/cormethodattr-enumeration.md) которое определяет атрибуты метода или глобальной функции.  
  
 `pvSigBlob`  
 (в) Подпись метода. Подпись сохраняется по мере поставки. Если вам необходимо указать дополнительную информацию по любым параметрам, используйте метод [IMetaDataEmit::SetParamProps.](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setparamprops-method.md)  
  
 `cbSigBlob`  
 (в) Количество байтов `pvSigBlob`в .  
  
 `ulCodeRVA`  
 (в) Адрес кода.  
  
 `dwImplFlags`  
 (в) Значение перечисления [CorMethodImpl,](../../../../docs/framework/unmanaged-api/metadata/cormethodimpl-enumeration.md) которое определяет особенности реализации метода.  
  
 `pmd`  
 (ваут) Символ участника.  
  
## <a name="remarks"></a>Remarks  
 API метаданных гарантирует сохранение методов в том же порядке, что и вызывающий абонент, испускающий `td` их для заданного класса или интерфейса, указанного в параметре.  
  
 Дополнительная информация `DefineMethod` об использовании и определенных параметрах приведена ниже.  
  
## <a name="slots-in-the-v-table"></a>Слоты в V-столе  
 Время выполнения использует определения метода для настройки слотов v-таблицы. В случае, когда один или несколько слотов необходимо пропустить, например, для сохранения паритета с макетом интерфейса COM, определяется манекен метод, чтобы занять слот или слоты в v-таблице; `dwMethodFlags` установить `mdRTSpecialName` значение перечисления [CorMethodAttr](../../../../docs/framework/unmanaged-api/metadata/cormethodattr-enumeration.md) и указать имя как:  
  
 _VtblGap\<*количество последовательностей*>\<\_*CountOfSlots*>
  
 где *SequenceNumber* — это номер последовательности метода, а *CountOfSlots* — это количество слотов, которые можно пропустить в v-таблице. Если *CountOfSlots* опущен, предполагается 1. Эти методы манекена не поддаются вызову ни из управляемого, ни из неуправляемого кода, и любая попытка вызвать их из управляемого или неуправляемого кода генерирует исключение. Их единственная цель состоит в том, чтобы занять место в v-таблице, которую генерирует время выполнения для интеграции COM.  
  
## <a name="duplicate-methods"></a>Двойные методы  
 Не следует определять дублирующие методы. То есть не стоит `DefineMethod` звонить с дублирующим набором значений в `td`, `wzName`и `pvSig` параметрах. (Эти три параметра вместе однозначно определяют метод.). Тем не менее, можно использовать дубликат тройной при условии, что для одного из определений метода вы установите `mdPrivateScope` бит в параметре. `dwMethodFlags` (Бит `mdPrivateScope` означает, что компилятор не будет излучать ссылку на это определение метода.)  
  
## <a name="method-implementation-information"></a>Информация о реализации метода  
 Информация о реализации метода часто неизвестна на момент декларируется методом. Таким образом, вам не нужно передавать `ulCodeRVA` `dwImplFlags` значения в `DefineMethod`и параметров при вызове . Значения могут быть поставлены позже через [IMetaDataEmit::SetMethodImplFlags](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setmethodimplflags-method.md) или [IMetaDataEmit::SetRVA](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setrva-method.md), в случае необходимости.  
  
 В некоторых ситуациях, таких как сценарии вызова платформы (PInvoke) или `ulCodeRVA` COM interop, тело метода не будет поставлено и должно быть установлено к нулю. В таких ситуациях метод не должен быть помечен как абстрактный, так как время выполнения будет находить реализацию.  
  
## <a name="defining-a-method-for-pinvoke"></a>Определение метода для PInvoke  
 Для того чтобы каждая неуправляемая функция вызывалась через PInvoke, необходимо определить управляемый метод, представляющий целевую неуправляемую функцию. Чтобы определить управляемый `DefineMethod` метод, используйте с некоторыми параметрами, установленными для определенных значений, в зависимости от способа использования PInvoke:  
  
- True PInvoke - включает в себя вызов внешнего неуправляемого метода, который находится в неуправляемом DLL.  
  
- Локальный PInvoke - включает в себя вызов родного неуправляемого метода, встроенного в текущий управляемый модуль.  
  
 Параметры приведены в следующей таблице.  
  
|Параметр|Значения для истинного PInvoke|Значения для локального PInvoke|  
|---------------|-----------------------------|------------------------------|  
|`dwMethodFlags`||Набор `mdStatic`; ясно `mdSynchronized` `mdAbstract`и .|  
|`pvSigBlob`|Допустимая подпись метода общего времени выполнения языка (CLR) с параметрами, которые являются действительными управляемыми типами.|Действующая подпись метода CLR с параметрами, которые являются действительными управляемыми типами.|  
|`ulCodeRVA`||0|  
|`dwImplFlags`|Задайте значения для `miCil` и `miManaged`.|Задайте значения для `miNative` и `miUnmanaged`.|  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** Cor.h  
  
 **Библиотека:** Используется в качестве ресурса в MSCorEE.dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- [Интерфейс IMetaDataEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [Интерфейс IMetaDataEmit2](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
