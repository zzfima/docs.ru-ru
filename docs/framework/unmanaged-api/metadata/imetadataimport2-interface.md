---
title: Интерфейс IMetaDataImport2
ms.date: 03/30/2017
api_name:
- IMetaDataImport2
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport2
helpviewer_keywords:
- IMetaDataImport2 interface [.NET Framework metadata]
ms.assetid: d39b2b87-ba53-4771-ae53-952a68452511
topic_type:
- apiref
ms.openlocfilehash: 0fd7915ef46899bdce8312bc6e8a466167e26382
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74429205"
---
# <a name="imetadataimport2-interface"></a>Интерфейс IMetaDataImport2
Расширяет интерфейс [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) для обеспечения возможности работы с универсальными типами.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод EnumGenericParamConstraints](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-enumgenericparamconstraints-method.md)|Возвращает перечислитель для массива ограничений универсальных параметров, связанных с универсальным параметром, представленным указанным токеном.|  
|[Метод EnumGenericParams](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-enumgenericparams-method.md)|Возвращает перечислитель для массива маркеров универсальных параметров, связанных с указанным маркером TypeDef или MethodDef.|  
|[Метод EnumMethodSpecs](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-enummethodspecs-method.md)|Возвращает перечислитель для массива токенов MethodSpec, связанных с указанным токеном MethodDef или MemberRef.|  
|[Метод GetGenericParamConstraintProps](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-getgenericparamconstraintprops-method.md)|Возвращает метаданные, связанные с ограничением универсального параметра, представленного указанным маркером ограничения.|  
|[Метод GetGenericParamProps](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-getgenericparamprops-method.md)|Возвращает метаданные, связанные с универсальным параметром, представленным указанным токеном.|  
|[Метод GetMethodSpecProps](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-getmethodspecprops-method.md)|Возвращает сигнатуру метаданных метода, на который ссылается указанный токен MethodSpec.|  
|[Метод GetPEKind](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-getpekind-method.md)|Возвращает значение, определяющее природу кода в переносимом исполняемом (PE) файле (обычно это DLL или EXE-файл), определенный в текущей области метаданных.|  
|[Метод GetVersionString](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-getversionstring-method.md)|Возвращает номер версии среды выполнения, которая использовалась для построения сборки.|  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** COR. h  
  
 **Библиотека:** Используется в качестве ресурса в MsCorEE. dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- <xref:System.Reflection.PortableExecutableKinds>
- [Интерфейсы метаданных](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)
- [Интерфейс IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
