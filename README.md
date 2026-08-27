# Database Design Lab 🛠️

Begleitendes Notebook zum Golem+ Artikel: **„Database Design in der KI-Ära: Warum alte Tugenden plötzlich Data-Projekte retten“**.

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/antogiro/database-design-lab/blob/main/database_design_lab.ipynb)

*(Klicken Sie auf den Badge, um das Labor direkt im Browser ohne lokale Installation auszuführen)*

## Darum geht es
Dieses Repository demonstriert mechanisch und messbar, warum naives Datenbank-Design („alles als Text“) moderne analytische Systeme und KI-Agenten ausbremst – und wie klassisches Handwerk (Typen, Constraints, physische Ordnung) dieses Problem löst.

**Das Besondere:** Sie müssen keine Gigabytes an CSV-Dateien herunterladen. Das Notebook generiert synthetische **3 Millionen Datensätze (Stellenanzeigen & Bewerbungen)** in wenigen Sekunden *on-the-fly* im Arbeitsspeicher.

## Was dieses Notebook demonstriert

1. **Naives vs. Designed Schema:** Der drastische Performance-Unterschied zwischen `VARCHAR`-Joins und typisierten `BIGINT`-Relationen.
2. **Der I/O-Beweis:** Sichtbarmachung von **Zone Map Pruning** (Block Skipping) via `EXPLAIN ANALYZE`. Wir zeigen, wie eine physische Datensortierung (ORDER BY) Full Table Scans eliminiert.
3. **Constraints als KI-Leitplanken:** Warum `CHECK`- und `UNIQUE`-Constraints zwingend nötig sind, um Halluzinationen bei Text-to-SQL-Modellen (LLMs) zu verhindern.
4. **Denormalisierung mit Maß:** Erstellung von hochperformanten Read Models für analytische Dashboards (Latenzen < 10 ms).
5. **Hybride Datenarchitektur & Vektorsuche:** Nativer Einsatz von Embeddings (Arrays) und HNSW-Vektorindizes direkt in der relationalen Engine – das Ende der dedizierten Vektor-Datenbanken.
6. **Der Semantic Layer:** Wie man Agenten über kuratierte Views (`analytics_postings`) eine fehlerfreie API bietet.

## Lokale Installation (falls nicht Colab genutzt wird)

Stellen Sie sicher, dass Python installiert ist. Klonen Sie das Repository und installieren Sie die Abhängigkeiten:

```bash
git clone https://github.com/DEIN_GITHUB_NAME/database-design-lab.git
cd database-design-lab
pip install -r requirements.txt
