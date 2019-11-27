---
title: Метод IMetaDataImport::FindMethod
ms.date: 03/30/2017
api_name:
- IMetaDataImport.FindMethod
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::FindMethod
helpviewer_keywords:
- FindMethod method [.NET Framework metadata]
- IMetaDataImport::FindMethod method [.NET Framework metadata]
ms.assetid: 0f9bde1d-e306-438d-941b-d0925b322304
topic_type:
- apiref
ms.openlocfilehash: 470b6511366cef1680eaf97f9ab376736add55c4
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74437900"
---
# <a name="imetadataimportfindmethod-method"></a>Метод IMetaDataImport::FindMethod
Возвращает указатель на токен MethodDef для метода, заключенного в указанном <xref:System.Type> и имеющего указанное имя и подпись метаданных.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT FindMethod (  
   [in]  mdTypeDef          td,  
   [in]  LPCWSTR            szName,   
   [in]  PCCOR_SIGNATURE    pvSigBlob,   
   [in]  ULONG              cbSigBlob,   
   [out] mdMethodDef        *pmb  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `td`  
 окне Токен `mdTypeDef` для типа (класса или интерфейса), который включает член для поиска. Если это значение равно `mdTokenNil`, поиск выполняется для глобальной функции.  
  
 `szName`  
 окне Имя искомого метода.  
  
 `pvSigBlob`  
 окне Указатель на сигнатуру двоичных метаданных метода.  
  
 `cbSigBlob`  
 окне Размер в байтах `pvSigBlob`.  
  
 `pmb`  
 заполняет Указатель на соответствующий токен MethodDef.  
  
## <a name="remarks"></a>Заметки  
 Метод указывается с помощью включающего класса или интерфейса (`td`), его имени (`szName`) и, при необходимости, его сигнатуры (`pvSigBlob`). В классе или интерфейсе может быть несколько методов с одинаковым именем. В этом случае передайте сигнатуру метода, чтобы найти уникальное совпадение.  
  
 Подпись, передаваемая `FindMethod`, должна быть создана в текущей области, так как сигнатуры привязаны к определенной области. Сигнатура может внедрять маркер, идентифицирующий включающий класс или тип значения. Токен является индексом локальной таблицы TypeDef. Нельзя построить подпись времени выполнения вне контекста текущей области и использовать эту сигнатуру в качестве входных данных для `FindMethod`.  
  
 `FindMethod` находит только методы, которые были определены непосредственно в классе или интерфейсе; Он не находит унаследованные методы.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** COR. h  
  
 **Библиотека:** Включается в качестве ресурса в библиотеку MsCorEE. dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также

- <xref:System.Reflection.MethodInfo>
- [Интерфейс IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [Интерфейс IMetaDataImport2](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
