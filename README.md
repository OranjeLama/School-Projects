import random

# --- Tool 1: Rekenmachine ---
def rekenmachine():
    print("--- Mini Rekenmachine ---")
    try:
        a = float(input("Geef het eerste getal: "))
        b = float(input("Geef het tweede getal: "))
        operator = input("Kies een operator (+, -, *, /): ")

        if operator == "+":
            return a + b
        elif operator == "-":
            return a - b
        elif operator == "*":
            return a * b
        elif operator == "/":
            if b != 0:
                return a / b
            else:
                return "Fout: delen door nul kan niet."
        else:
            return "Ongeldige operator."
    except ValueError:
        return "Fout: voer een geldig getal in."

# --- Tool 2: Balans-check gamen vs school ---
def balans(uren_gamen, uren_school):
    if uren_gamen > uren_school:
        return "Je gamet meer dan je aan school werkt — misschien even opletten!"
    elif uren_gamen == uren_school:
        return "Je hebt een goede balans tussen gamen en school."
    else:
        return "Goed bezig! Je besteedt meer tijd aan school dan gamen."

# --- Tool 3: Raadspel light ---
def raadspel():
    print("--- Raadspel ---")
    geheim = random.randint(1, 10)
    gok = int(input("Raad een getal tussen 1 en 10: "))

    if gok == geheim:
        print("Goed geraden!")
    else:
        print(f"Helaas, het getal was {geheim}.")

# --- Menu lus ---
def menu():
    while True:
        print("\nKies een optie:")
        print("1. Rekenmachine")
        print("2. Balans-check gamen vs school")
        print("3. Raadspel")
        print("4. Stoppen")

        keuze = input("Maak je keuze (1-4): ")

        if keuze == "1":
            resultaat = rekenmachine()
            print("Uitkomst:", resultaat)
        elif keuze == "2":
            try:
                gamen = float(input("Hoeveel uur per week game je? "))
                school = float(input("Hoeveel uur per week doe je schoolwerk? "))
                advies = balans(gamen, school)
                print("Advies:", advies)
            except ValueError:
                print("Fout: voer geldige uren in.")
        elif keuze == "3":
            raadspel()
        elif keuze == "4":
            print("Programma gestopt.")
            break
        else:
            print("Ongeldige keuze, probeer opnieuw.")

# Programma starten
if __name__ == "__main__":
    menu()
