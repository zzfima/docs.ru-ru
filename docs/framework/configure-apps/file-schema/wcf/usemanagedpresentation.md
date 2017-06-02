---
title: "&lt;useManagedPresentation&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 17a0dd77-af54-41db-a9d0-4b17ff42878f
caps.latest.revision: 5
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 5
---
# &lt;useManagedPresentation&gt;
Элемент привязки, используемый для связи со службой маркеров безопасности CardSpace, которая поддерживает CardSpace\-профиль WS\-Trust.  Этот элемент не имеет атрибутов и представлен как пустой переключатель.  
  
## Синтаксис  
  
```  
  
<useManagedPresentation/>  
```  
  
## Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### Атрибуты  
 Отсутствует.  
  
### Дочерние элементы  
 Нет  
  
### Родительские элементы  
  
|Элемент|Описание|  
|-------------|--------------|  
|[\<привязка\>](../../../../../docs/framework/misc/binding.md)|Определяет все возможности пользовательской привязки.|  
  
## Заметки  
 Этот элемент используется поставщиком удостоверения для отражения в своей политике поддержки CardSpace\-профиля WS\-Trust.  Поставщики удостоверений, которые предоставляют такое утверждение политики, должны быть способны выдавать маркеры на основе этого профиля CardSpace.  
  
## См. также  
 <xref:System.ServiceModel.Configuration.UseManagedPresentationElement>   
 <xref:System.ServiceModel.Channels.UseManagedPresentationBindingElement>   
 <xref:System.ServiceModel.Channels.CustomBinding>   
 [Привязки](../../../../../docs/framework/wcf/bindings.md)   
 [Расширение привязок](../../../../../docs/framework/wcf/extending/extending-bindings.md)   
 [Пользовательские привязки](../../../../../docs/framework/wcf/extending/custom-bindings.md)   
 [\<customBinding\>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)