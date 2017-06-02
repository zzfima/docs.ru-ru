---
title: "Отображение идентификаторов объектов на криптографические алгоритмы | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "криптографические алгоритмы"
  - "шифрование, сопоставление идентификаторов объекта"
  - "цифровые подписи"
  - "идентификаторы, сопоставление идентификаторов объекта"
  - "сопоставление идентификаторов объекта"
ms.assetid: c9673f81-bf9e-47fd-bc6f-6bc1c1c4c15e
caps.latest.revision: 8
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 8
---
# Отображение идентификаторов объектов на криптографические алгоритмы
Цифровая подпись гарантирует сохранность данных при их передаче между программами.  Обычно цифровая подпись вычисляется путем применения математической функции к хэш\-коду данных, к которым применяется подпись.  При форматировании подписываемого хэш\-кода некоторые алгоритмы цифровой подписи добавляют в операцию форматирования идентификатор объекта \(OID\) ASN.1.  OID идентифицирует алгоритм, использованный для вычисления хэш\-кода.  Для включения применения пользовательских алгоритмов в криптографический механизм можно сопоставить алгоритмы с идентификаторами объектов.  В следующем примере показан способ сопоставления идентификатора объекта с новым хэш\-алгоритмом.  
  
```  
<configuration>  
   <mscorlib>  
      <cryptographySettings>  
         <cryptoNameMapping>  
            <cryptoClasses>  
               <cryptoClass MyNewHash="MyNewHashClass, MyAssembly  
                  Culture='en', PublicKeyToken=a5d015c7d5a0b012,  
                  Version=1.0.0.0"/>  
            </cryptoClasses>  
            <nameEntry name="NewHash" class="MyNewHash"/>  
         </cryptoNameMapping>  
         <oidMap>  
            <oidEntry OID="1.3.14.33.42.46"  name="NewHash"/>  
         </oidMap>  
      </cryptographySettings>  
   </mscorlib>  
</configuration>  
```  
  
 Элемент [\<oidEntry\>](../../../docs/framework/configure-apps/file-schema/cryptography/oidentry-element.md) содержит два атрибута.  Атрибут **OID** — это идентификатор объекта \(число\).  Атрибут **name** — это значение атрибута **name** из элемента [\<nameEntry\>](../../../docs/framework/configure-apps/file-schema/cryptography/nameentry-element.md).  Перед сопоставлением идентификатора объекта с простым именем необходимо сопоставить имя алгоритма с классом.  
  
## См. также  
 [Настройка криптографических классов](../../../docs/framework/configure-apps/configure-cryptography-classes.md)   
 [Службы криптографии](../../../docs/standard/security/cryptographic-services.md)