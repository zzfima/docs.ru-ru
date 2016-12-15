---
title: "Ссылка &lt;ссылка&gt; на дружественную сборку является недопустимой | Microsoft Docs"
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
  - "vbc31535"
  - "bc31535"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC31535"
ms.assetid: 6540c1d0-bb19-4051-a579-2e4f9094585e
caps.latest.revision: 5
caps.handback.revision: 5
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Ссылка &lt;ссылка&gt; на дружественную сборку является недопустимой
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Ссылка \<ссылка\> на дружественную сборку является недопустимой.В подписанных со строгим именем сборках необходимо указать открытый ключ в их объявлениях InternalsVisibleTo.  
  
 Имя сборки, передаваемое конструктору атрибута <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>, идентифицирует сборку со строгим именем, но она не содержит атрибут `PublicKey`.  
  
 **Идентификатор ошибки**: BC31535  
  
### Чтобы исправить эту ошибку  
  
1.  Определите открытый ключ для дружественной сборки со строгими именами.  Включите открытый ключ в имя сборки, передаваемой конструктору атрибута <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> с помощью атрибута `PublicKey`.  
  
## См. также  
 <xref:System.Reflection.AssemblyName>   
 [Дружественные сборки](../Topic/Friend%20Assemblies%20\(C%23%20and%20Visual%20Basic\).md)   
 [Практическое руководство. Создание подписанных дружественных сборок](../Topic/How%20to:%20Create%20Signed%20Friend%20Assemblies%20\(C%23%20and%20Visual%20Basic\).md)