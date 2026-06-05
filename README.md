# SIGA - Sistema Inteligente de Guia ao Atendimento

**Mapeamento Indoor por Wi-Fi Fingerprinting | IoT, Engenharia de Dados e IA na Saúde**

---

## 📄 Sobre o Projeto

O **SIGA** é um protótipo funcional de **Posicionamento Indoor baseado em Wi-Fi Fingerprinting**. O sistema foi concebido para resolver o desafio de geolocalização em ambientes fechados (onde o GPS tradicional não funciona), permitindo rastrear a distribuição de equipes assistenciais e a movimentação de ativos críticos dentro de uma infraestrutura hospitalar complexa.

### 🏠 Validação em Ambiente Controlado (Simulação)
Como os testes iniciais foram executados em arquitetura residencial, o sistema foi calibrado para mapear os cômodos da casa simulando **alas e setores estratégicos de um pronto-socorro**:
* **Sala de TV** ➡️ Simulando a **Recepção e Triagem**
* **Sala de Jantar** ➡️ Simulando a **Ala de Triagem Clínica**
* **Cozinha** ➡️ Simulando a **Recepção de Abertura de Fichas**
* **Quarto 1** ➡️ Simulando o **Consultório Médico**
* **Quarto 2** ➡️ Simulando a **Observação Adulto/Pediátrica**
* **Quarto 3** ➡️ Simulando a **Sala de Radiologia (Raio-X)**

---

## 🗺️ Roadmap de Desenvolvimento do Ecossistema

O projeto está dividido em 3 grandes fases de entrega:

### 🟩 Fase 1: Engenharia de Dados & Coleta (Concluída - Este Repositório)
* Desenvolvimento do script em Python usando `subprocess` e `netsh wlan` para varredura de redes em tempo real.
* Interface interativa com `ipywidgets` para coleta e calibração por setor (*Modo Offline*).
* Pipeline de dados que limpa, pivota as tabelas (transformando roteadores/BSSIDs em colunas) e substitui sinais ausentes por `0`.
* **Privacidade & LGPD:** Sistema de anonimização automática que converte MAC addresses reais em tokens estritos (`Antena_01`, `Antena_02`), blindando a infraestrutura de vizinhos antes de subir os dados para o GitHub.

### 🟨 Fase 2: Inteligência Artificial & Treinamento (Próximo Passo)
* Construção do dataset consolidado (`dataset_wifi_hospital_clean.csv`).
* Treinamento de modelos de Classificação (como *Random Forest*, *KNN* ou *SVM*) para aprenderem a "assinatura de radiofrequência" de cada setor hospitalar.
* Avaliação de métricas de acurácia matemática para garantir que a IA diferencie perfeitamente o Consultório da Observação com base apenas no poder do sinal Wi-Fi.

### 🟦 Fase 3: Página Web do Paciente & Painel Gerencial (Futuro)
* Desenvolvimento de uma aplicação web responsiva.
* **Visão do Gestor:** Painel de controle em tempo real exibindo a volumetria e tempos de permanência da equipe assistencial em cada setor.
* **Visão do Paciente:** Uma página web segura onde o acompanhante ou o próprio paciente consegue acompanhar o status da sua jornada e a localização estimada do seu atendimento dentro do fluxo hospitalar.

---

## 📂 Estrutura de Arquivos Atual

