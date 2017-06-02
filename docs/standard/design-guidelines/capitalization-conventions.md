---
title: "Правила использования прописных букв | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "имена с чередованием регистра [платформа .NET Framework]"
  - "Класс рекомендации по разработке библиотек [платформа .NET Framework], регистр букв"
  - "Имена стиле Pascal [платформа .NET Framework]"
  - "учет регистра букв"
  - "имена [платформа .NET Framework], регистр букв"
ms.assetid: 4c4ea526-9203-486f-b72d-29d61c5b3c6d
caps.latest.revision: 16
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 16
---
# Правила использования прописных букв
Правила, описанные в этой главе размещать простой метод с помощью варианта, при применении согласованно, создание идентификаторов для типов, членов и параметров, удобном для чтения.  
  
## Правила использования прописных букв для идентификаторов  
 Чтобы различать слова в идентификаторе, преобразование первой буквы каждого слова в идентификаторе. Не используйте символы подчеркивания для различения слова, или на то пошло, в любом месте идентификаторов. Существует два способа соответствующего идентификатора в зависимости от использования идентификатора к прописным:  
  
-   PascalCasing  
  
-   camelCasing  
  
 PascalCasing соглашение, все идентификаторы, за исключением имен параметров, первая буква каждого слова \(включая акронимов через из двух букв\), как показано в следующих примерах:  
  
 `PropertyDescriptor`   
 `HtmlTag`  
  
 Особым случаем совершается двухбуквенных акронимах, в которых заданы оба буквы, как показано в следующий идентификатор:  
  
 `IOStream`  
  
 CamelCasing соглашение, используется только для имен параметров, первая буква каждого слова, кроме первого, как показано в следующих примерах. Как показано в примере, двухбуквенных акронимах, которые начинаются с идентификатора Camel находятся нижнего регистра.  
  
 `propertyDescriptor`   
 `ioStream`   
 `htmlTag`  
  
 **✓ сделать** использовать PascalCasing для всех открытых члена типа и пространство имен имен, состоящих из нескольких слов.  
  
 **✓ сделать** использовать camelCasing для имен параметров.  
  
 Следующая таблица описывает правила использования прописных букв для различных типов идентификаторов.  
  
|Идентификатор|Регистр|Пример|  
|-------------------|-------------|------------|  
|Пространство имен|Стиль языка Pascal|`namespace System.Security { ... }`|  
|Тип|Стиль языка Pascal|`public class StreamReader { ... }`|  
|Интерфейс|Стиль языка Pascal|`public interface IEnumerable { ... }`|  
|Метод|Стиль языка Pascal|`public class Object {` <br />  `public virtual string ToString();` <br /> `}`|  
|Свойство|Стиль языка Pascal|`public class String {` <br />  `public int Length { get; }` <br /> `}`|  
|Событие|Стиль языка Pascal|`public class Process {` <br />  `public event EventHandler Exited;` <br /> `}`|  
|Поле|Стиль языка Pascal|`public class MessageQueue {` <br />  `public static readonly TimeSpan` <br /> `InfiniteTimeout;` <br /> `}` <br /> `public struct UInt32 {` <br />  `public const Min = 0;` <br /> `}`|  
|Значение перечисления|Стиль языка Pascal|`public enum FileMode {` <br />  `Append,` <br />  `...` <br /> `}`|  
|Параметр|Camel|`public class Convert {` <br />  `public static int ToInt32(string value);` <br /> `}`|  
  
## Использование составных слов и общие термины  
 Большинство составные термины обрабатываются как отдельные слова в целях использования прописных букв.  
  
 **X не** прописных так называемые составные слова закрытия формы.  
  
 Это сложные слова, записываются в одно слово, например конечной точки. С целью правила учета регистра считайте составное слово единым одно слово. Используете текущий словарь для определения, если является составным словом записывается в виде закрытых.  
  
|Стиль языка Pascal|Camel|Не|  
|------------------------|-----------|--------|  
|`BitFlag`|`bitFlag`|`Bitflag`|  
|`Callback`|`callback`|`CallBack`|  
|`Canceled`|`canceled`|`Cancelled`|  
|`DoNot`|`doNot`|`Don't`|  
|`Email`|`email`|`EMail`|  
|`Endpoint`|`endpoint`|`EndPoint`|  
|`FileName`|`fileName`|`Filename`|  
|`Gridline`|`gridline`|`GridLine`|  
|`Hashtable`|`hashtable`|`HashTable`|  
|`Id`|`id`|`ID`|  
|`Indexes`|`indexes`|`Indices`|  
|`LogOff`|`logOff`|`LogOut`|  
|`LogOn`|`logOn`|`LogIn`|  
|`Metadata`|`metadata`|`MetaData, metaData`|  
|`Multipanel`|`multipanel`|`MultiPanel`|  
|`Multiview`|`multiview`|`MultiView`|  
|`Namespace`|`namespace`|`NameSpace`|  
|`Ok`|`ok`|`OK`|  
|`Pi`|`pi`|`PI`|  
|`Placeholder`|`placeholder`|`PlaceHolder`|  
|`SignIn`|`signIn`|`SignOn`|  
|`SignOut`|`signOut`|`SignOff`|  
|`UserName`|`userName`|`Username`|  
|`WhiteSpace`|`whiteSpace`|`Whitespace`|  
|`Writable`|`writable`|`Writeable`|  
  
## Учет регистра  
 Языки, которые могут выполняться в среде CLR не обязаны поддерживать чувствительность к регистру, хотя некоторые сделать. Даже если ее поддерживает язык других языков, которые могут получить доступ к вашей платформы не происходит. Интерфейсы API, доступные извне, таким образом, нельзя полагаться на случай для различения двух имен в том же контексте.  
  
 **X не** предполагается, что все языки программирования чувствительны к регистру. Они не являются. Имена не могут различаться только регистром.  
  
 *Частей © 2005, 2009 корпорации Microsoft. Все права защищены.*  
  
 *Воспроизведены разрешении Пирсон образования, Inc. из [Framework рекомендации по проектированию: условные обозначения, стили и шаблоны для повторного использования библиотеки .NET, второе издание](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina и Брэд Абрамс опубликованы 22 октября 2008 г., издательство Addison\-Wesley Professional как часть цикла разработки Microsoft Windows.*  
  
## См. также  
 [Рекомендации по проектированию Framework](../../../docs/standard/design-guidelines/index.md)   
 [Правила именования](../../../docs/standard/design-guidelines/naming-guidelines.md)