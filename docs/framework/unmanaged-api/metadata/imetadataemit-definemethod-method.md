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
ms.openlocfilehash: c46b075341742aac605537a08b762b3cf47ef35b
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74431807"
---
# <a name="imetadataemitdefinemethod-method"></a>Метод IMetaDataEmit::DefineMethod
Создает определение для метода или глобальной функции с указанной сигнатурой и возвращает маркер в это определение метода.  
  
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
 окне Маркер `mdTypedef` родительского класса или родительского интерфейса метода. Задайте для параметра `td` значение `mdTokenNil`, если вы определяете глобальную функцию.  
  
 `szName`  
 окне Имя члена в Юникоде.  
  
 `dwMethodFlags`  
 окне Значение перечисления [кормесодаттр](../../../../docs/framework/unmanaged-api/metadata/cormethodattr-enumeration.md) , определяющее атрибуты метода или глобальной функции.  
  
 `pvSigBlob`  
 окне Сигнатура метода. Подпись сохраняется, как указано. Если необходимо указать дополнительные сведения для всех параметров, используйте метод [IMetaDataEmit:: сетпарампропс](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setparamprops-method.md) .  
  
 `cbSigBlob`  
 окне Число байтов в `pvSigBlob`.  
  
 `ulCodeRVA`  
 окне Адрес кода.  
  
 `dwImplFlags`  
 окне Значение перечисления [кормесодимпл](../../../../docs/framework/unmanaged-api/metadata/cormethodimpl-enumeration.md) , указывающее функции реализации метода.  
  
 `pmd`  
 заполняет Токен элемента.  
  
## <a name="remarks"></a>Примечания  
 API метаданных гарантирует сохранение методов в том же порядке, в котором вызывающий объект создает их для данного включающего класса или интерфейса, указанного в параметре `td`.  
  
 Дополнительные сведения об использовании `DefineMethod` и определенных параметрах параметров приведены ниже.  
  
## <a name="slots-in-the-v-table"></a>Слоты в таблице V-Table  
 Среда выполнения использует определения методов для настройки слотов v-table. В случае, когда необходимо пропустить один или несколько слотов, например для сохранения четности с помощью макета COM-интерфейса, будет определен фиктивный метод, который занимает область или слоты в таблице v-table. Задайте для `dwMethodFlags` значение `mdRTSpecialName` перечисления [кормесодаттр](../../../../docs/framework/unmanaged-api/metadata/cormethodattr-enumeration.md) и укажите имя:  
  
 _VtblGap\<*SequenceNumber*>\<\_*каунтофслотс*>
  
 где *SequenceNumber* — порядковый номер метода, а *каунтофслотс* — число слотов для пропуска в таблице v-table. Если *каунтофслотс* опущен, то предполагается значение 1. Эти фиктивные методы не могут быть вызываемыми из управляемого или неуправляемого кода и любая попытка их вызова из управляемого или неуправляемого кода создает исключение. Их единственная задача состоит в том, чтобы освободить место в таблице v-table, которую среда выполнения создает для интеграции COM.  
  
## <a name="duplicate-methods"></a>Дублирующиеся методы  
 Не следует определять дублирующиеся методы. То есть не следует вызывать `DefineMethod` с повторяющимися наборами значений в параметрах `td`, `wzName`и `pvSig`. (Эти три параметра вместе уникально определяют метод.) Однако можно использовать повторяющееся тройное значение, если для одного из определений методов задается бит `mdPrivateScope` в параметре `dwMethodFlags`. (Бит `mdPrivateScope` означает, что компилятор не будет создавать ссылку на это определение метода.)  
  
## <a name="method-implementation-information"></a>Сведения о реализации метода  
 Сведения о реализации метода часто неизвестны во время объявления метода. Поэтому при вызове `DefineMethod`не нужно передавать значения в параметры `ulCodeRVA` и `dwImplFlags`. Значения можно указать позже с помощью [IMetaDataEmit:: сетмесодимплфлагс](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setmethodimplflags-method.md) или [IMetaDataEmit:: SetRVA](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setrva-method.md).  
  
 В некоторых ситуациях, например при вызове платформы (PInvoke) или в сценариях COM-взаимодействия, тело метода не будет передано, а `ulCodeRVA` должно быть установлено в нулевое значение. В таких ситуациях метод не должен помечаться как абстрактный, поскольку среда выполнения обнаружит реализацию.  
  
## <a name="defining-a-method-for-pinvoke"></a>Определение метода для PInvoke  
 Для вызова каждой неуправляемой функции через PInvoke необходимо определить управляемый метод, представляющий целевую неуправляемую функцию. Чтобы определить управляемый метод, используйте `DefineMethod` с некоторыми параметрами, заданными определенными значениями, в зависимости от способа использования PInvoke:  
  
- True PInvoke — включает вызов внешнего неуправляемого метода, который находится в неуправляемой библиотеке DLL.  
  
- Локальный PInvoke — включает вызов собственного неуправляемого метода, внедренного в текущий управляемый модуль.  
  
 Параметры параметров приведены в следующей таблице.  
  
|Параметр|Значения для истинного PInvoke|Значения для локального вызова PInvoke|  
|---------------|-----------------------------|------------------------------|  
|`dwMethodFlags`||Задайте `mdStatic`; Очистите `mdSynchronized` и `mdAbstract`.|  
|`pvSigBlob`|Допустимая сигнатура метода общеязыковой среды выполнения (CLR) с параметрами, которые являются допустимыми управляемыми типами.|Допустимая сигнатура метода CLR с параметрами, которые являются допустимыми управляемыми типами.|  
|`ulCodeRVA`||0|  
|`dwImplFlags`|Задайте `miCil` и `miManaged`.|Задайте `miNative` и `miUnmanaged`.|  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** COR. h  
  
 **Библиотека:** Используется в качестве ресурса в MSCorEE. dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также:

- [Интерфейс IMetaDataEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [Интерфейс IMetaDataEmit2](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
