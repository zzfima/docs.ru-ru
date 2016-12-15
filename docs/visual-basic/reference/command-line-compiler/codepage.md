---
title: "/codepage (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "/codepage - параметр компилятора [Visual Basic]"
  - "codepage - параметр компилятора [Visual Basic]"
  - "-codepage - параметр компилятора [Visual Basic]"
ms.assetid: be36ec33-6800-4505-838c-4124564f5cc9
caps.latest.revision: 17
caps.handback.revision: 17
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# /codepage (Visual Basic)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Задает кодовую страницу, которая должна использоваться для всех файлов исходного кода при компиляции.  
  
## Синтаксис  
  
```  
/codepage:id  
```  
  
## Аргументы  
  
|||  
|-|-|  
|Термин|Определение|  
|`id`|Обязательное.  Компилятор использует кодовую страницу, определяемую параметром `id` для интерпретации кодировки исходных файлов.|  
  
## Заметки  
 Для компиляции исходного кода, сохраненного в определенной кодировке, можно использовать ключевое слово `/codepage`, чтобы указать, какую кодовую страницу следует использовать.  Параметр`/codepage` применяется ко всем файлам при компиляции исходного кода.  Дополнительные сведения см. в разделе [Кодировки в .NET Framework](../Topic/Character%20Encoding%20in%20the%20.NET%20Framework.md).  
  
 Параметр `/codepage` не нужен, если файлы исходного кода были сохранены с помощью текущей кодовой страницы ANSI, юникод или UTF\-8 с подписью.  [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)] сохраняет все файлы исходного кода с текущей кодовой страницей ANSI по умолчанию, если пользователь не указывает другую кодировку в диалоговом окне **Кодировка**.  [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)] использует диалоговое окно **Кодировка** для открытия файлов исходного кода, сохраненных с другой кодовой страницей.  
  
> [!NOTE]
>  Параметр `/codepage` недоступен из среды разработки [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)]; он доступен только при компиляции из командной строки.  
  
## См. также  
 [Компилятор Visual Basic с интерфейсом командной строки](../../../visual-basic/reference/command-line-compiler/index.md)