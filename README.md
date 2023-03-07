# Realidade Aumentada Unity

### Aplicação Simples de Realidade Aumentada com Unity + Vuphoria
 
Este projeto utiliza o Unity e o Vuforia, que viabilizam o uso de realidade aumentada.

### Para começar, será necessário baixar o Vuforia Engine
[Baixar o Vuforia](https://developer.vuforia.com/user/login?url=/downloads/sdk%3F_%3D1678117884)

Será preciso criar uma conta e uma licença para registrar o alvo (target).

Após subir o alvo desejado, será possível visualizar o mapeamento como na imagem abaixo:

<img width="500" src="https://i.ibb.co/zFQyWR8/print1.jpg">

Feito isso, basta baixar o banco de dados.

Em seguida, monte sua centa com o Imagem Target e a Câmera AR:

<img width="500" src="https://i.ibb.co/02L13Dk/Anima-o.gif">

#### O script para rotacionar o Cubo

```csharp
using System.Collections;
using System.Collections.Generic;
using UnityEngine;

public class rotate : MonoBehaviour
{
    public Vector3 rotateAmount;
    void Start()
    {
        
    }

    void Update()
    {
        transform.Rotate(rotateAmount * Time.deltaTime);
    }
}
```
