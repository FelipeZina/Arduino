// Definições
const int pinoPIR = 2;
bool cronometroRodando = false;
unsigned long tempoInicial = 0;
unsigned long tempoFinal = 0;

void setup() {
  pinMode(pinoPIR, INPUT);
  Serial.begin(9600);
  Serial.println("--- Sistema Pronto: Aguardando primeiro movimento ---");
}

void loop() {
  int leitura = digitalRead(pinoPIR);

  if (leitura == HIGH) {
    
    if (!cronometroRodando) {
      tempoInicial = millis();
      cronometroRodando = true;
      Serial.println("Movimento 1 detectado! Timer INICIADO...");
      
      delay(2000); 
    } 
    
    else {
      tempoFinal = millis();
      cronometroRodando = false;
      
      unsigned long duracao = tempoFinal - tempoInicial;
      float segundos = duracao / 1000.0;
      
      Serial.print("Movimento 2 detectado! Timer PARADO.");
      Serial.print(" Tempo decorrido: ");
      Serial.print(segundos);
      Serial.println(" segundos.");
      Serial.println("----------------------------------------------");
      
      delay(3000);
      Serial.println("Aguardando novo ciclo...");
    }
  }
}
