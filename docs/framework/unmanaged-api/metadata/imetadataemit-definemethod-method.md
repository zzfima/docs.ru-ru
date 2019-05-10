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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 4879af90aa06515a95b4d15f039ff3c2b1a88f62
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/28/2019
ms.locfileid: "64664998"
---
# <a name="imetadataemitdefinemethod-method"></a>Метод IMetaDataEmit::DefineMethod
Создает определение для метода или глобальной функции с указанной сигнатурой и возвращает маркер для этого определения метода.  
  
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
  
## <a name="parameters"></a>Параметры  
 `td`  
 [in] `mdTypedef` Маркеров родительского класса или интерфейса родительского метода. Задайте `td` для `mdTokenNil`, при определении глобальной функции.  
  
 `szName`  
 [in] Имя в формате Юникод.  
  
 `dwMethodFlags`  
 [in] Значение [CorMethodAttr](../../../../docs/framework/unmanaged-api/metadata/cormethodattr-enumeration.md) перечисление, указывающее атрибуты метода или глобальной функции.  
  
 `pvSigBlob`  
 [in] Сигнатура метода. Сигнатура сохраняется как предоставляемые. Если вам нужно указать дополнительную информацию для любых параметров, используйте [IMetaDataEmit::SetParamProps](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setparamprops-method.md) метод.  
  
 `cbSigBlob`  
 [in] Число байт в `pvSigBlob`.  
  
 `ulCodeRVA`  
 [in] Адрес кода.  
  
 `dwImplFlags`  
 [in] Значение [CorMethodImpl](../../../../docs/framework/unmanaged-api/metadata/cormethodimpl-enumeration.md) перечисления, которое указывает возможности реализации метода.  
  
 `pmd`  
 [out] Токен члена.  
  
## <a name="remarks"></a>Примечания  
 API метаданных гарантирует сохранения методы в порядке их выдает вызывающий объект данного включающего класса или интерфейса, который указан в параметре `td` параметра.  
  
 Дополнительные сведения, касающиеся использования `DefineMethod` и определенных настроек параметров приведены ниже.  
  
## <a name="slots-in-the-v-table"></a>Слоты в таблице V  
 Среда выполнения использует определения методов для настройки ячеек виртуальной таблицы. В случае, когда один или несколько слотов должны быть пропущена, например для сохранения четности в структуре COM-интерфейса пустой метод определен должна занимать одну ячейку или ячейки в v таблице. Задайте `dwMethodFlags` для `mdRTSpecialName` значение [CorMethodAttr](../../../../docs/framework/unmanaged-api/metadata/cormethodattr-enumeration.md) перечисления и укажите имя как:  
  
 _VtblGap\<*SequenceNumber*>\<\_*CountOfSlots*>
  
 где *SequenceNumber* регистрационный номер транзакции метода и *числоЯчеек* Число слотов для пропуска в таблице v. Если *числоЯчеек* — этот параметр опущен, используется значение 1. Эти пустые методы не вызываются в управляемом и неуправляемом коде, и любая попытка их вызова из управляемый или неуправляемый код, создает исключение. Единственное их назначение — занять место в v таблице, то среда выполнения создает для COM-интеграции.  
  
## <a name="duplicate-methods"></a>Дублирующиеся методы  
 Не следует определять повторяющиеся методы. То есть, не следует вызывать `DefineMethod` с набором повторяющихся значений в `td`, `wzName`, и `pvSig` параметров. (Эти три параметра однозначно определяют метод.). Тем не менее, можно использовать повторяющиеся тройку условии, что для одного из определений метода, задайте `mdPrivateScope` бит в `dwMethodFlags` параметра. ( `mdPrivateScope` Бита означает, что компилятор не выдает ссылку на определение этого метода.)  
  
## <a name="method-implementation-information"></a>Сведения о реализации метода  
 Сведения о реализации метода часто не известны во время объявления. Таким образом, не нужно передавать значения в `ulCodeRVA` и `dwImplFlags` параметров при вызове `DefineMethod`. Значения могут передаваться в более поздней версии с помощью [IMetaDataEmit::SetMethodImplFlags](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setmethodimplflags-method.md) или [IMetaDataEmit::SetRVA](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setrva-method.md), соответствующим образом.  
  
 В некоторых ситуациях, например вызова неуправляемого кода (PInvoke) или в сценариях COM-взаимодействия, не следует указывать тело метода, и `ulCodeRVA` должно быть равным нулю. В этих случаях метод не должен использоваться как абстрактный, так как среда выполнения будет искать реализацию.  
  
## <a name="defining-a-method-for-pinvoke"></a>Определение метода для PInvoke  
 Для каждой неуправляемой функции, вызываемый посредством PInvoke необходимо определить управляемый метод, представляющий целевую неуправляемую функцию. Для определения управляемого метода используется `DefineMethod` с некоторыми параметры, заданные для определенных значений, в зависимости от того, в котором используется PInvoke:  
  
- True PInvoke — включает вызов внешнего неуправляемого метода, который находится в неуправляемой библиотеки DLL.  
  
- Локальный PInvoke — включает вызов метода машинного неуправляемые, внедренного в текущий управляемый модуль.  
  
 Настройки параметров приведены в следующей таблице.  
  
|Параметр|Значения true PInvoke|Значения для локальной PInvoke|  
|---------------|-----------------------------|------------------------------|  
|`dwMethodFlags`||Задайте `mdStatic`; Очистить `mdSynchronized` и `mdAbstract`.|  
|`pvSigBlob`|Допустимая распространенных языковой среды исполнения (CLR) сигнатура метода с параметрами, которые являются допустимыми управляемых типов.|Действительная подпись метода среды CLR с параметрами, которые являются допустимыми управляемых типов.|  
|`ulCodeRVA`||0|  
|`dwImplFlags`|Задайте `miCil` и `miManaged`.|Задайте `miNative` и `miUnmanaged`.|  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** Cor.h  
  
 **Библиотека:** Используется как ресурс в MSCorEE.dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс IMetaDataEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [Интерфейс IMetaDataEmit2](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
