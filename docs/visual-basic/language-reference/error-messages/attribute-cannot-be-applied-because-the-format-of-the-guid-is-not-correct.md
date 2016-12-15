---
title: "&lt;атрибут&gt; не может быть применен из-за неверного формата GUID &lt;номер&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vbc32500"
  - "bc32500"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC32500"
ms.assetid: 6fa34c55-368e-4d7d-b488-07a3fffe045f
caps.latest.revision: 10
caps.handback.revision: 10
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &lt;атрибут&gt; не может быть применен из-за неверного формата GUID &lt;номер&gt;
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

В блоке атрибутов `COMClassAttribute` задан идентификатор GUID, который не соответствует правильному формату GUID.  В `COMClassAttribute` идентификаторы GUID используются для уникального определения класса, интерфейса и события создания.  
  
 GUID состоит из 16 байтов, первые восемь из которых являются числовыми, а последние восемь — двоичными.  Он создается с помощью служебных программ Microsoft, таких, как uuidgen.exe; его уникальность гарантируется в пространстве и времени.  
  
 **Идентификатор ошибки:** BC32500  
  
### Чтобы исправить эту ошибку  
  
1.  Определите один или несколько правильных идентификаторов GUID, необходимых для идентификации COM\-объекта.  
  
2.  Убедитесь, что строки GUID, представленные в блоке атрибутов `COMClassAttribute`, скопированы правильно.  
  
## См. также  
 <xref:System.Guid>   
 [Атрибуты](../Topic/Attributes%20\(C%23%20and%20Visual%20Basic\).md)