import 'package:flutter/material.dart';

void main() => runApp(MyApp());

class MyApp extends StatelessWidget {
  const MyApp({super.key});

  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      home: Scaffold(
        backgroundColor: Colors.grey[200],
        body: Center(
          child: EventItem(
            date: "10 JUNE",
            title: "International Band Mu...",
            location: "36 Guild Street London, UK",
            imagePath: "assets/hands.png", // Ensure the image is in your assets folder
          ),
        ),
      ),
    );
  }
}

class EventItem extends StatelessWidget {
  final String date;
  final String title;
  final String location;
  final String imagePath;

  const EventItem({
    super.key,
    required this.date,
    required this.title,
    required this.location,
    required this.imagePath,
  });

  @override
  Widget build(BuildContext context) {
    return SizedBox(
      width: 169,
      height: 290,
      child: Stack(
        alignment: Alignment.center,
        children: [
          EventItemImage(imagePath: imagePath),
          // Positioned the date and bookmark icon over the image
          Positioned(
            top: 10,
            left: 10,
            child: Container(
              padding: const EdgeInsets.symmetric(horizontal: 10, vertical: 5),
              decoration: BoxDecoration(
                color: Colors.white,
                borderRadius: BorderRadius.circular(8),
              ),
              child: Text(
                date,
                style: const TextStyle(
                  color: Colors.red,
                  fontWeight: FontWeight.bold,
                  fontSize: 12,
                ),
              ),
            ),
          ),
          Positioned(
            top: 10,
            right: 10,
            child: Container(
              padding: const EdgeInsets.all(6),
              decoration: const BoxDecoration(
                color: Colors.white,
                shape: BoxShape.circle,
              ),
              child: const Icon(
                Icons.bookmark,
                color: Colors.red,
              ),
            ),
          ),
          // The Event Information (title and location) will be below the image
          Positioned(
            bottom: 0,
            child: EventItemInfo(
              title: title,
              location: location,
            ),
          ),
        ],
      ),
    );
  }
}

class EventItemImage extends StatelessWidget {
  final String imagePath;

  const EventItemImage({super.key, required this.imagePath});

  @override
  Widget build(BuildContext context) {
    return ClipRRect(
      borderRadius: BorderRadius.circular(13),
      child: SizedBox(
        width: 169,
        height: 153,
        child: Image.asset(
          imagePath,
          fit: BoxFit.cover,
        ),
      ),
    );
  }
}

class EventItemInfo extends StatelessWidget {
  final String title;
  final String location;

  const EventItemInfo({super.key, required this.title, required this.location});

  @override
  Widget build(BuildContext context) {
    return Container(
      width: 169,
      padding: const EdgeInsets.all(10),
      decoration: BoxDecoration(
        color: Colors.white,
        borderRadius: BorderRadius.vertical(bottom: Radius.circular(13)),
      ),
      child: Column(
        crossAxisAlignment: CrossAxisAlignment.start,
        children: [
          Text(
            title,
            style: const TextStyle(
              fontWeight: FontWeight.bold,
              fontSize: 14,
            ),
            maxLines: 1,
            overflow: TextOverflow.ellipsis,
          ),
          SizedBox(height: 5),
          Text(
            location,
            style: const TextStyle(
              fontSize: 12,
              color: Colors.grey,
            ),
            maxLines: 2,
            overflow: TextOverflow.ellipsis,
          ),
        ],
      ),
    );
  }
}
