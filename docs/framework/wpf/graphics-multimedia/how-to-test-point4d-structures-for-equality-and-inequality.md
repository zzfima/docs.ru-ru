---
title: "Практическое руководство. Проверка структур Point4D на равенство и неравенство | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "равенство, проверка структур Point4D на"
  - "неравенство, проверка структур Point4D на"
  - "Point4D - структуры, проверка на равенство"
  - "Point4D - структуры, проверка на неравенство"
  - "проверка, проверка структур Point4D на равенство"
  - "проверка, проверка структур Point4D на неравенство"
ms.assetid: e004a67e-db7f-4af8-a31f-e6b2a44ccf34
caps.latest.revision: 8
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 8
---
# Практическое руководство. Проверка структур Point4D на равенство и неравенство
В этом примере демонстрируется проверка структур <xref:System.Windows.Media.Media3D.Point4D> на равенство и неравенство.  
  
 В следующем коде показано, как проверить структуры <xref:System.Windows.Media.Media3D.Point4D> на равенство и неравенство с помощью методов равенства <xref:System.Windows.Media.Media3D.Point4D>.  Структуры <xref:System.Windows.Media.Media3D.Point4D> вначале проверяются на равенство с помощью перегруженного оператора равенства \(`==`\), а затем — на неравенство с помощью перегруженного оператора неравенства \(`!=`\). После этого структуры <xref:System.Windows.Media.Media3D.Point3D> и <xref:System.Windows.Media.Media3D.Point4D> проверяются на равенство с помощью статического метода <xref:System.Windows.Media.Media3D.Point4D.Equals%2A>.  
  
## Пример  
 [!code-csharp[3DGallery_procedural_snip#Point4DEqualityExample_csharp](../../../../samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_procedural_snip/CSharp/Misc3DOperationsExample.cs#point4dequalityexample_csharp)]  
  
## См. также  
 <xref:System.Windows.Media.Media3D.Point4D.op_Equality%2A>   
 <xref:System.Windows.Media.Media3D.Point4D.op_Inequality%2A>   
 <xref:System.Windows.Media.Media3D.Point4D.Equals%2A>