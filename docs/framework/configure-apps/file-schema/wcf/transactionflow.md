---
title: <transactionFlow>
ms.date: 03/30/2017
ms.assetid: 8c7b4c5b-ace3-4fe3-89ff-7b13c9aacd13
ms.openlocfilehash: 2d1008a4308c9fda5d2291ce704d1f19205e996a
ms.sourcegitcommit: 581ab03291e91983459e56e40ea8d97b5189227e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/27/2019
ms.locfileid: "70041253"
---
# <a name="transactionflow"></a>\<transactionFlow >
Задает поддержку потока транзакций для пользовательской привязки.  
  
 \<> System. serviceModel  
\<привязки >  
\<customBinding >  
\<Привязка >  
\<transactionFlow >  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<transactionFlow transactionProtocol="OleTransactions/WSAtomicTransactionOctober2004" />
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
  
|Атрибут|Описание|  
|---------------|-----------------|  
|transactionProtocol|Задает используемый протокол транзакций. Допустимы следующие значения:<br /><br /> -OleTransactions<br />-WSAtomicTransactionOctober2004<br /><br /> Значение по умолчанию - OleTransactions.<br /><br /> Это атрибут типа <xref:System.ServiceModel.TransactionProtocol>.|  
  
### <a name="child-elements"></a>Дочерние элементы  
 Нет.  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<Привязка >](../../../misc/binding.md)|Определяет все возможности пользовательской привязки.|  
  
## <a name="remarks"></a>Примечания  
 Этот элемент позволяет включить или отключить входящий поток транзакций в параметрах привязки конечной точки, а также задать необходимый формат протокола для входящих транзакций. Дополнительные сведения об использовании этого элемента конфигурации см. в разделе [Конфигурация транзакций ServiceModel](../../../wcf/feature-details/servicemodel-transaction-configuration.md) и [Включение потока транзакций](../../../wcf/feature-details/enabling-transaction-flow.md).  
  
> [!CAUTION]
> При использовании протокола `OleTransactions` для реализации потока транзакций от одной конечной точки к другой время ожидания транзакции может быть потеряно, если целевая конечная точка попытается запустить поток снова, используя любой протокол, отличный от `OleTransactions`. Это может привести к тому, что время ожидания для всех узлов, находящихся ниже перехода OleTransactions, окажется больше, чем ожидалось.  
  
## <a name="see-also"></a>См. также

- <xref:System.ServiceModel.Configuration.TransactionFlowElement>
- <xref:System.ServiceModel.Channels.TransactionFlowBindingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [Конфигурация транзакции ServiceModel](../../../wcf/feature-details/servicemodel-transaction-configuration.md)
- [Включение потока транзакций](../../../wcf/feature-details/enabling-transaction-flow.md)
- [Привязки](../../../wcf/bindings.md)
- [Расширение привязок](../../../wcf/extending/extending-bindings.md)
- [Пользовательские привязки](../../../wcf/extending/custom-bindings.md)
- [\<customBinding >](custombinding.md)
