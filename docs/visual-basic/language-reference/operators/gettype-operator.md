---
title: "Оператор GetType (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.GetType"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "GetType - ключевое слово"
  - "GetType - оператор"
ms.assetid: 4f733297-2503-4607-850c-15eba65fff90
caps.latest.revision: 17
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 17
---
# Оператор GetType (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/includes/vs2017banner.md)]

Возвращает объект <xref:System.Type> для указанного типа.  Объект <xref:System.Type> предоставляет сведения о типе, например о его свойствах, методах и событиях.  
  
## Синтаксис  
  
```  
GetType(typename)  
```  
  
#### Параметры  
  
|||  
|-|-|  
|Параметр|Описание|  
|`typename`|Имя типа, о котором необходимы сведения.|  
  
## Заметки  
 Оператор `GetType` возвращает объект <xref:System.Type> для заданного `typename`.  Имя любого типа можно передать в `typename`.  К ним относятся следующие.  
  
-   Любой тип данных Visual Basic, например `Boolean` или `Date`.  
  
-   Любые классы, структуры, модули или интерфейсы .NET Framework, например <xref:System.ArgumentException?displayProperty=fullName> или <xref:System.Double?displayProperty=fullName>.  
  
-   Любой класс, структура, модуль или интерфейс, определяемый приложением.  
  
-   Любой массив, определяемый приложением.  
  
-   Любой делегат, определяемый приложением.  
  
-   Все перечисления, определяемые Visual Basic, .NET Framework или приложением.  
  
 Если нужно получить объект типа объектной переменной, используйте метод <xref:System.Type.GetType%2A?displayProperty=fullName>.  
  
 Оператор `GetType` может быть полезным в следующих случаях.  
  
-   Необходимо получить доступ к метаданным типа во время выполнения.  Объект <xref:System.Type> предоставляет такие метаданные, как члены типа и сведения о развертывании.  Это необходимо, например, чтобы отобразить сборку.  Дополнительные сведения см. в разделе <xref:System.Reflection?displayProperty=fullName>.  
  
-   Требуется сравнить две ссылки на объекты, чтобы проверить, ссылаются ли они на экземпляры одного типа.  Если это так, `GetType` возвращает ссылку на тот же объект <xref:System.Type>.  
  
## Пример  
 В следующих примерах показано использование оператора `GetType`.  
  
 [!code-vb[VbVbalrOperators#26](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/gettype-operator_1.vb)]  
  
## См. также  
 [Порядок применения операторов в Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)   
 [Список операторов, сгруппированных по функциональному назначению](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)   
 [Операторы и выражения](../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)