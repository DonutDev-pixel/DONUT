# DONUT
    import matplotlib.pyplot as plt

    # Data for the donut chart
    labels = ['Category A', 'Category B', 'Category C', 'Category D']
    sizes = [15, 30, 45, 10]
    colors = ['gold', 'yellowgreen', 'lightcoral', 'lightskyblue']

    # Create the donut chart
    fig1, ax1 = plt.subplots()
    ax1.pie(sizes, colors=colors, labels=labels, autopct='%1.1f%%', startangle=90, pctdistance=0.85)

    # Draw a white circle in the center to create the donut effect
    centre_circle = plt.Circle((0,0),0.70,fc='white')
    fig = plt.gcf()
    fig.gca().add_artist(centre_circle)

    # Equal aspect ratio ensures that pie is drawn as a circle.
    ax1.axis('equal')
    plt.title('Donut Chart Example')
    plt.show()
