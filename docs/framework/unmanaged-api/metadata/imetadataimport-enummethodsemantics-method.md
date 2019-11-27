---
title: Метод IMetaDataImport::EnumMethodSemantics
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumMethodSemantics
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumMethodSemantics
helpviewer_keywords:
- EnumMethodSemantics method [.NET Framework metadata]
- IMetaDataImport::EnumMethodSemantics method [.NET Framework metadata]
ms.assetid: e7e3c630-9691-46d6-94df-b5593a7bb08a
topic_type:
- apiref
ms.openlocfilehash: ff6932b6040a19e0ccda2f8d2140fa131cdd9224
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74450074"
---
# <a name="imetadataimportenummethodsemantics-method"></a>Метод IMetaDataImport::EnumMethodSemantics
Перечисляет свойства и события их изменения, с которыми связан указанный метод.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT EnumMethodSemantics (  
   [in, out] HCORENUM    *phEnum,  
   [in]  mdMethodDef     mb,   
   [out] mdToken         rEventProp[],  
   [in]  ULONG           cMax,  
   [out] ULONG           *pcEventProp  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `phEnum`  
 [вход, выход] Указатель на перечислитель. При первом вызове этого метода это значение должно быть равно NULL.  
  
 `mb`  
 окне Токен MethodDef, ограничивающий область перечисления.  
  
 `rEventProp`  
 заполняет Массив, используемый для хранения событий или свойств.  
  
 `cMax`  
 [in] Максимальный размер массива `rEventProp`.  
  
 `pcEventProp`  
 заполняет Количество событий или свойств, возвращаемых в `rEventProp`.  
  
## <a name="return-value"></a>Возвращаемое значение  
  
|HRESULT|Описание|  
|-------------|-----------------|  
|`S_OK`|`EnumMethodSemantics` успешно возвращено.|  
|`S_FALSE`|Нет событий или свойств для перечисления. В этом случае `pcEventProp` равно нулю.|  
  
## <a name="remarks"></a>Примечания  
 Многие типы среды CLR определяют события`Changed` *свойств* и `On`*свойства*`Changed` методы, связанные с их свойствами. Например, тип <xref:System.Windows.Forms.Control?displayProperty=nameWithType> определяет свойство <xref:System.Windows.Forms.Control.Font%2A>, <xref:System.Windows.Forms.Control.FontChanged> событие и метод <xref:System.Windows.Forms.Control.OnFontChanged%2A>. Метод доступа set свойства <xref:System.Windows.Forms.Control.Font%2A> вызывает метод <xref:System.Windows.Forms.Control.OnFontChanged%2A>, который, в свою очередь, вызывает событие <xref:System.Windows.Forms.Control.FontChanged>. Можно вызвать `EnumMethodSemantics` с помощью MethodDef для <xref:System.Windows.Forms.Control.OnFontChanged%2A>, чтобы получить ссылки на свойство <xref:System.Windows.Forms.Control.Font%2A> и на событие <xref:System.Windows.Forms.Control.FontChanged>.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** COR. h  
  
 **Библиотека:** Включается в качестве ресурса в библиотеку MsCorEE. dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [Интерфейс IMetaDataImport2](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
