---
title: <useManagedPresentation>
ms.date: 03/30/2017
ms.assetid: 17a0dd77-af54-41db-a9d0-4b17ff42878f
ms.openlocfilehash: e67cc316b8747ee785055ceb4f954988fa82a44c
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69940613"
---
# <a name="usemanagedpresentation"></a>\<Усеманажедпресентатион >
Элемент привязки, используемый для связи со службой маркеров безопасности CardSpace, которая поддерживает CardSpace-профиль WS-Trust. Этот элемент не имеет атрибутов и представлен как пустой переключатель.  
  
 \<> System. serviceModel  
\<привязки >  
\<customBinding >  
\<Привязка >  
\<Усеманажедпресентатион >  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<useManagedPresentation />
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
 Нет.  
  
### <a name="child-elements"></a>Дочерние элементы  
 Отсутствуют  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<Привязка >](../../../misc/binding.md)|Определяет все возможности пользовательской привязки.|  
  
## <a name="remarks"></a>Примечания  
 Этот элемент используется поставщиком удостоверения для отражения в своей политике поддержки CardSpace-профиля WS-Trust. Поставщики удостоверений, которые предоставляют такое утверждение политики, должны быть способны выдавать маркеры на основе этого профиля CardSpace.  
  
## <a name="see-also"></a>См. также

- <xref:System.ServiceModel.Configuration.UseManagedPresentationElement>
- <xref:System.ServiceModel.Channels.UseManagedPresentationBindingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [Привязки](../../../wcf/bindings.md)
- [Расширение привязок](../../../wcf/extending/extending-bindings.md)
- [Пользовательские привязки](../../../wcf/extending/custom-bindings.md)
- [\<customBinding >](custombinding.md)
