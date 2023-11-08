# Tugas Metode Numerik
Dosen Pengampu : Anggay Luri Pramana M.Kom, dengan Tugas materi SPNL-Regula Falsi
# SPNL-Regula Falsi 
Metode Regula Falsi ini adalah solusi sistem persamaan non linear untuk menentukan akar persamaan dengan cara memanfaatkan kemiringan dan selisih tinggi dari selang. Cara kerja metode ini prinsipnya hampir sama dengan metode bisection yaitu menggunakan iterasi dengan memperbarui selangnya, tapi bedanya dirumus c.
# Code dari Metode Regula Falsi 
def f(x):
    return x**2 - 6*x + 5

def find_root_bisection(a, b, tolerance):
    if f(a) * f(b) >= 0:
        print("Tidak ada akar dalam selang ini.")
        return None
    
    while (b - a) / 2 > tolerance:
        midpoint = (a + b) / 2
        if f(midpoint) == 0:
            return round(midpoint, 3)
        elif f(a) * f(midpoint) < 0:
            b = midpoint
        else:
            a = midpoint
    
    return round((a + b) / 2, 3)

a = 3
b = 6
tolerance = 0.001

root = find_root_bisection(a, b, tolerance)
if root is not None:
    print(f"Akar persamaan f(x) = x^2 - 6x + 5 = 0 dalam selang [{a}, {b}] adalah {root}")

# Hasil Code
Hasil dari perhitungan code diatas yaitu (5,0)
