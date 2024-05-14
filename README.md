# Criando-Projeto-para-Consultar-a-Previs-o-do-Tempo-via-API

Vamos criar um projeto modular para consultar a previsão do tempo usando Angular e uma API externa. Aqui está um exemplo de como você pode estruturar seu texto e código:

---

**Introdução ao Projeto de Previsão do Tempo com Angular**

O desenvolvimento de aplicações web modernas exige não apenas conhecimento em programação, mas também a habilidade de integrar diversas tecnologias para criar soluções eficientes e robustas. Neste projeto, vamos aprofundar nossos conhecimentos em **Angular**, um framework poderoso para construção de interfaces de usuário, e aprenderemos a consumir dados de uma **API externa** para apresentar a previsão do tempo.

**Módulos e Estrutura do Projeto**

O projeto será dividido em módulos para manter o código organizado e facilitar a manutenção. A seguir, descrevemos os módulos principais:

1. **Módulo de Configuração (AppModule):**
   - Importação de módulos necessários.
   - Definição de rotas.
   - Configuração de serviços globais.

2. **Módulo de Serviços (WeatherService):**
   - Comunicação com a API externa.
   - Tratamento de dados recebidos.
   - Exposição de dados para componentes.

3. **Módulo de Componentes:**
   - **WeatherComponent:** Exibe a previsão do tempo.
   - **CitySelectorComponent:** Permite a seleção da cidade.

**Consumindo a API Externa**

Para consumir a API externa, utilizaremos o serviço `HttpClient` do Angular. Veja um exemplo de como implementar o `WeatherService`:

```typescript
import { Injectable } from '@angular/core';
import { HttpClient } from '@angular/common/http';
import { Observable } from 'rxjs';

@Injectable({
  providedIn: 'root'
})
export class WeatherService {
  private apiUrl = 'https://api.weatherapi.com/v1/current.json';

  constructor(private http: HttpClient) {}

  getWeather(city: string): Observable<any> {
    const params = { q: city, key: 'SUA_CHAVE_API' };
    return this.http.get(this.apiUrl, { params });
  }
}
```

**Conclusão**

Ao final deste projeto, você terá uma aplicação Angular funcional que consome dados de uma API de previsão do tempo, demonstrando a integração entre front-end e serviços externos. Este conhecimento é essencial para o desenvolvimento web moderno e abre portas para a criação de soluções ainda mais complexas e interessantes.

---

Espero que este exemplo ajude a dar uma ideia clara de como abordar o projeto. Lembre-se de substituir `'SUA_CHAVE_API'` pela chave real fornecida pela API de previsão do tempo que você decidir usar.
