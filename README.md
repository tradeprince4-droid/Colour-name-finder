# Colour-name-finderNAMES = {
    "burnt sienna": "#E97451", "forest green": "#228B22", "midnight blue": "#191970",
    "coral": "#FF7F50", "lavender": "#E6E6FA", "mustard": "#FFDB58",
    "teal": "#008080", "crimson": "#DC143C", "slate": "#708090", "ivory": "#FFFFF0",
}

def rgb(h):
    h = h.lstrip("#")
    return tuple(int(h[i:i+2], 16) for i in (0, 2, 4))

def nearest(h):
    t = rgb(h)
    return min(NAMES, key=lambda n: sum((a - b) ** 2 for a, b in zip(t, rgb(NAMES[n]))))

print(nearest("#E0663A"))  # burnt sienna
