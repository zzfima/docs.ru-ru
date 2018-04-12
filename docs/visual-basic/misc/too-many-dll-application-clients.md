---
title: Слишком много приложений-клиентов DLL
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbrID47
ms.assetid: 4b87780b-67ad-4c96-9253-db954a751dad
caps.latest.revision: 8
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: d4b9278134e937ac8bf4626237954432d727ac0d
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="too-many-dll-application-clients"></a>Слишком много приложений-клиентов DLL
Библиотека динамической компоновки (DLL) для [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] может обеспечить доступ ограниченному числу ведущих приложений. Ваше приложение и другие приложения, которые являются узлами [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] (к некоторым из которых может обращаться ваше приложение), пытаются получить доступ к библиотеке DLL [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] одновременно.  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
-   Уменьшите число открытых приложений, обращающихся к [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)].  
  
## <a name="see-also"></a>См. также  
 [Типы ошибок](../../visual-basic/programming-guide/language-features/error-types.md)
