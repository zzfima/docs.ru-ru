---
title: "Метод IMetaDataEmit::DefineMethod"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataEmit.DefineMethod
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataEmit::DefineMethod
helpviewer_keywords:
- DefineMethod method [.NET Framework metadata]
- IMetaDataEmit::DefineMethod method [.NET Framework metadata]
ms.assetid: 3e2102c5-48b7-4c0e-b805-7e2b5e156e3d
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 4fa136f5e6669e58ef709db5b53f538804cfcac2
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataemitdefinemethod-method"></a>Метод IMetaDataEmit::DefineMethod
Создает определение для метода или глобальной функции с заданной подписью и возвращает маркер для этого определения метода.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
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
  
#### <a name="parameters"></a>Параметры  
 `td`  
 [in] `mdTypedef` Маркеров родительского класса или интерфейса родительского метода. Задать `td` для `mdTokenNil`, при определении глобальной функции.  
  
 `szName`  
 [in] Имя члена в кодировке Юникод.  
  
 `dwMethodFlags`  
 [in] Значение [CorMethodAttr](../../../../docs/framework/unmanaged-api/metadata/cormethodattr-enumeration.md) перечисление, указывающее атрибуты метода или глобальной функции.  
  
 `pvSigBlob`  
 [in] Сигнатура метода. Сигнатура сохраняется, как указано. Если вам нужно указать дополнительную информацию для всех параметров, используйте [IMetaDataEmit::SetParamProps](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setparamprops-method.md) метод.  
  
 `cbSigBlob`  
 [in] Число байт в `pvSigBlob`.  
  
 `ulCodeRVA`  
 [in] Адрес кода.  
  
 `dwImplFlags`  
 [in] Значение [CorMethodImpl](../../../../docs/framework/unmanaged-api/metadata/cormethodimpl-enumeration.md) перечисления, которое указывает возможности реализации метода.  
  
 `pmd`  
 [out] Токен члена.  
  
## <a name="remarks"></a>Примечания  
 API метаданных гарантирует сохранения методы в порядке их выдает вызывающий объект для данного включающего класса или интерфейса, который указывается в `td` параметра.  
  
 Дополнительные сведения по использованию `DefineMethod` и определенных настроек параметров приведены ниже.  
  
## <a name="slots-in-the-v-table"></a>Слоты в таблице V  
 Среда выполнения использует определения методов для настройки ячеек виртуальной таблицы. Там, где один или несколько слотов должны быть пропущена, например для сохранения четности в структуре COM-интерфейса пустой метод определяется должна занимать одну ячейку или ячейки таблицы v. задать `dwMethodFlags` для `mdRTSpecialName` значение [CorMethodAttr](../../../../docs/framework/unmanaged-api/metadata/cormethodattr-enumeration.md) перечисления и укажите имя как:  
  
 _VtblGap\<*SequenceNumber*>\<\_*числоЯчеек*>  
  
 где *SequenceNumber* является номером последовательности метода и *числоЯчеек* Число слотов для пропуска в виртуальной таблице. Если *числоЯчеек* — этот параметр опущен, используется значение 1. Эти пустые методы не вызываются в управляемом и неуправляемом коде, и любая попытка их вызова из управляемого или неуправляемого кода, создается исключение. Их единственной целью является занимают место в виртуальной таблице, созданной средой выполнения для COM-интеграции.  
  
## <a name="duplicate-methods"></a>Повторяющиеся методы  
 Не следует определять повторяющиеся методы. То есть, не следует вызывать `DefineMethod` с набором повторяющихся значений в `td`, `wzName`, и `pvSig` параметров. (Эти три параметра однозначно определяют метод.). Тем не менее, можно использовать повторяющиеся triple условии, что для одного из определений метода, задайте `mdPrivateScope` бит в `dwMethodFlags` параметра. ( `mdPrivateScope` Бита означает, что компилятор не будет выдавать ссылку на это определение метода.)  
  
## <a name="method-implementation-information"></a>Сведения о реализации метода  
 Сведения о реализации метода часто не известны во время объявления метода. Таким образом, необязательно для передачи значений в `ulCodeRVA` и `dwImplFlags` параметров при вызове `DefineMethod`. Значения могут передаваться с использованием более поздней версии [IMetaDataEmit::SetMethodImplFlags](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setmethodimplflags-method.md) или [IMetaDataEmit::SetRVA](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setrva-method.md)соответствующим образом.  
  
 В некоторых ситуациях, например вызова неуправляемого кода (PInvoke) или в сценариях COM-взаимодействия, не следует указывать тело метода, и `ulCodeRVA` должен быть равен нулю. В таких ситуациях метод не должен использоваться как абстрактный, поскольку среда выполнения будет искать реализацию.  
  
## <a name="defining-a-method-for-pinvoke"></a>Определение метода для PInvoke  
 Для каждой неуправляемой функции, вызываемый посредством PInvoke необходимо определить управляемый метод, представляющий целевую неуправляемую функцию. Для определения управляемого метода, используйте `DefineMethod` некоторые параметры, заданные для определенных значений, в зависимости от того, в котором используется PInvoke:  
  
-   Истинный PInvoke — включает вызов внешнего неуправляемого метода, который находится в неуправляемой библиотеке DLL.  
  
-   Локальный PInvoke — включает вызов метода машинного кода неуправляемый, встроенного в текущий управляемый модуль.  
  
 Настройки параметров приведены в следующей таблице.  
  
|Параметр|Значения true PInvoke|Значения для локального PInvoke|  
|---------------|-----------------------------|------------------------------|  
|`dwMethodFlags`||Задать `mdStatic`; снимите `mdSynchronized` и `mdAbstract`.|  
|`pvSigBlob`|Допустимая общих языка среды CLR сигнатура метода с параметрами, которые являются допустимыми управляемых типов.|Допустимая сигнатура метода среды CLR с параметрами, которые являются допустимыми управляемых типов.|  
|`ulCodeRVA`||0|  
|`dwImplFlags`|Задать `miCil` и `miManaged`.|Задать `miNative` и `miUnmanaged`.|  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** Cor.h  
  
 **Библиотека:** используется как ресурс в MSCorEE.dll  
  
 **Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Интерфейс IMetaDataEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [Интерфейс IMetaDataEmit2](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
