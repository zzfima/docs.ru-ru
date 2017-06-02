---
title: "Имена сборок и библиотек DLL | Microsoft Docs"
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
  - "имена [платформа .NET Framework] библиотек DLL"
  - "имена [платформа .NET Framework] сборок"
  - "сборки [платформа .NET Framework], имена"
  - "Имена библиотек DLL"
ms.assetid: e800b610-31b4-4949-9c14-cb60e9f254be
caps.latest.revision: 11
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 11
---
# Имена сборок и библиотек DLL
Сборка является единицей развертывания и удостоверение для управляемого кода программы. Хотя сборки могут охватывать один или несколько файлов, обычно сборки однозначное сопоставление с библиотекой DLL. Таким образом в этом разделе описывается только DLL соглашения об именовании, которые затем могут быть сопоставлены с соглашениями об именовании сборок.  
  
 **✓ сделать** выбирайте имена DLL\-библиотек, которые предложить больших фрагментов функции, такие как System.Data сборки.  
  
 Имена сборок и DLL не обязательно должны соответствовать именам пространств имен, но имеет смысл следовать имя пространства имен, при именовании сборок. Хорошее правило является имя библиотеки DLL, исходя из общего префикса сборок, содержащихся в сборке. Например, сборки с двумя пространствами имен `MyCompany.MyTechnology.FirstFeature` и `MyCompany.MyTechnology.SecondFeature`, можно вызвать `MyCompany.MyTechnology.dll`.  
  
 **✓ Рассмотрите ВОЗМОЖНОСТЬ** об именовании библиотек DLL по следующему шаблону:  
  
 `<Company>.<Component>.dll`  
  
 где `<Component>` содержит одно или несколько предложений, разделенных точкой. Например:  
  
 `Litware.Controls.dll`.  
  
 *Частей © 2005, 2009 корпорации Microsoft. Все права защищены.*  
  
 *Воспроизведены разрешении Пирсон образования, Inc. из [Framework рекомендации по проектированию: условные обозначения, стили и шаблоны для повторного использования библиотеки .NET, второе издание](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina и Брэд Абрамс опубликованы 22 октября 2008 г., издательство Addison\-Wesley Professional как часть цикла разработки Microsoft Windows.*  
  
## См. также  
 [Рекомендации по проектированию Framework](../../../docs/standard/design-guidelines/index.md)   
 [Правила именования](../../../docs/standard/design-guidelines/naming-guidelines.md)