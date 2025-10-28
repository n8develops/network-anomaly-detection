# network anomaly detection

watch all traffic and yell when something’s weird  

---

## datasets

**NSL-KDD** – from competition, not real traffic  
**CIC-IDS 2017** – closer to real, simulates actual network behavior  
- DoS  
- Brute Force  
- Data exfiltration  
- Infiltration  

---

## packets

tiny chunks of data with raw info  
too many packets = slow connection  
packet floods = maybe attack  

---

## what to look at

- duration → long connection?  
- source/dest IP → irregular?  
- protocol → certain type more sus?  
- bytes sent / received  
- packets per second  
- failed logins  

---

## model idea

given this connection → tell me if it’s attack or normal  

### supervised classification
(train on labeled data)
- random forest  
- gradient boosted trees  
- neural networks  

pros: high accuracy on known attacks  
cons: weak on new ones  

### unsupervised anomaly detection
(no labels, just figure out what’s weird)
- isolation forest  
- autoencoder  

pros: can catch unknown attacks  
cons: more false positives  

---

## notes

- if duration is tiny but packets are high → weird  
- if destination keeps changing → suspicious  
- normal traffic can look weird sometimes  
- tradeoff: accuracy vs generalization  

---

## quick thought

supervised → “this is known, find same again”  
unsupervised → “this looks off, investigate”  
