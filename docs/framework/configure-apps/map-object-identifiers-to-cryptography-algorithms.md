---
title: Отображение идентификаторов объектов на криптографические алгоритмы
ms.date: 03/30/2017
helpviewer_keywords:
- digital signatures
- identifiers, mapping object identifiers
- cryptographic algorithms
- mapping object identifiers
- cryptography, mapping object identifiers
ms.assetid: c9673f81-bf9e-47fd-bc6f-6bc1c1c4c15e
ms.openlocfilehash: a5aebac2d392d4540581dfe7c7afff0819968ac0
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69912546"
---
# <a name="mapping-object-identifiers-to-cryptography-algorithms"></a>Отображение идентификаторов объектов на криптографические алгоритмы
Цифровые подписи гарантируют, что данные не были изменены при отправке из одной программы в другую. Обычно цифровая подпись вычислена путем применения математической функции к хэшу подписываемых данных. При форматировании хэш-значения для подписи некоторые алгоритмы цифровых подписей добавляют в операцию форматирования идентификатор объекта ASN. 1 (OID). OID определяет алгоритм, который использовался для вычисления хэша. Вы можете сопоставлять алгоритмы с идентификаторами объектов, чтобы расширить механизм криптографии для использования пользовательских алгоритмов. В следующем примере показано, как сопоставлять идентификатор объекта с новым алгоритмом хэширования.  
  
```xml  
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
  
 [Элемент > оидентрисодержитдваатрибута.\<](./file-schema/cryptography/oidentry-element.md) Атрибут **OID** — это номер идентификатора объекта. Атрибут **Name** — это значение [ \<атрибута Name из элемента элементе nameentry >](./file-schema/cryptography/nameentry-element.md). Необходимо сопоставить имя алгоритма с классом, чтобы идентификатор объекта можно было сопоставить с простым именем.  
  
## <a name="see-also"></a>См. также

- [Настройка криптографических классов](configure-cryptography-classes.md)
- [Cryptographic Services](../../standard/security/cryptographic-services.md)
