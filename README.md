class Vector4D:
    def __init__(self, x, y, z, w):
        self.x = x
        self.y = y
        self.z = z
        self.w = w

    def __str__(self):
        components = []
        if self.x != 0:
            components.append(f'{self.x}x')
        if self.y != 0:
            components.append(f'{self.y}y')
        if self.z != 0:
            components.append(f'{self.z}z')
        if self.w != 0:
            components.append(f'{self.w}w')
        return '+'.join(components).replace('+-', '-')

    def magnitude(self):
        return (self.x**2 + self.y**2 + self.z**2 + self.w**2) ** 0.5

    def is_unit_vector(self):
        mag_squared = self.x**2 + self.y**2 + self.z**2 + self.w**2
        return mag_squared == 1

    def dot_product(self, other):
        return self.x * other.x + self.y * other.y + self.z * other.z + self.w * other.w

    def __sub__(self, other):
        return Vector4D(self.x - other.x, self.y - other.y, self.z - other.z, self.w - other.w)

    def __neg__(self):
        return Vector4D(-self.x, -self.y, -self.z, -self.w)

    def __repr__(self):
        return f"Vector4D(x={self.x}, y={self.y}, z={self.z}, w={self.w})"

v1 = Vector4D(3, -4, 6, 1)
v2 = Vector4D(1, 2, 3, 4)

print(v1)
print("Magnitude:", v1.magnitude())
print("Is unit vector:", v1.is_unit_vector())
print("Dot product with v2:", v1.dot_product(v2))
print("Difference from v2:", v1 - v2)
print("Additive inverse:", -v1)
